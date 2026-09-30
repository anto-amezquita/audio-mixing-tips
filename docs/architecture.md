# architecture.md

## Purpose

This file defines the stable technical rules of the product.

Feature specs may describe implementation details for one piece of work. This document defines the shared architecture that should remain consistent across the whole product.

The goal is to help contributors and AI agents make technical decisions that fit the system rather than solving each task in isolation.

---

## 1. Stack

### Frontend

- framework: Next.js, App Router
- language: TypeScript, strict mode
- styling: design-system tokens; CSS Modules or the design system's own styling approach for anything local
- component system: `@amezquita/design-system` from npm
- animation: none required; if needed, whatever the design system already uses
- forms: none — the only inputs are a search field and filter controls
- state management: React state plus URL query string; no state library
- data fetching: none at runtime — all content is read at build time
- routing: single route (`/`)

### Backend

None. The site is statically generated and has no server, database, auth, file storage, background jobs, or outbound mail. Any proposal that introduces one of these needs an ADR first.

### Tooling

- package manager: npm
- linting: ESLint with the Next.js config
- formatting: Prettier
- testing: Vitest for the content layer and the split script; no component test suite for v1
- CI/CD: Vercel's own build on push
- deployment: Vercel, from `main`

---

## 2. Repository structure

```txt
content/
  tricks/              # 100 markdown files, one per trick
  categories.json      # category slugs, labels, order, intro routines
source/
  mixing-tricks-library.md   # the original document the tricks were split from
scripts/
  split-library.ts     # one-off: source document -> content/tricks/
src/
  app/                 # Next.js App Router
  components/          # components local to this project
  lib/
    content.ts         # reads and validates content at build time
    schema.ts          # Zod schemas for frontmatter
    favourites.ts      # local-storage read/write
```

### Structure rules

- Content never lives in code. A trick's text belongs in `content/tricks/`, never in a component or a constant.
- `source/` is an archive. Nothing reads it at build or runtime after the split has run.
- `scripts/` holds one-off tooling. It is not part of the built site.
- Anything the design system already provides is imported, not re-implemented locally.

---

## 3. Architectural principles

#### Content is data, not markup

Tricks are parsed, validated and typed before a component sees them. A component receives a `Trick` object; it never parses markdown itself.

#### Fail the build, not the page

An invalid frontmatter field breaks `next build`. A typo in a category slug must never silently drop an entry from a filter.

#### Everything renders at build time

All 100 entries are in the HTML. Search and filters hide and show what is already there. Nothing user-facing waits on a network request.

#### Reuse the design system before writing a component

If `@amezquita/design-system` has it, use it. A local component needs a reason.

#### Optimize for clarity before cleverness

This is a single-page static site. Any abstraction that makes it harder to read than that is the wrong abstraction.

---

## 4. Frontend architecture

### Routing

One route, `/`. Filters and search are reflected in the query string so a filtered view can be bookmarked and shared.

### Rendering model

Static generation. Content is read from disk at build time. No ISR, no server components fetching at request time.

### State management

- **URL query string** — active search term, category filter, device filter, favourites toggle. This is the source of truth for anything a user might want to link to.
- **React local state** — which entries are expanded.
- **Local storage** — the favourites list, read after mount.

No global state library. No server state.

### Data fetching

None at runtime. `lib/content.ts` reads `content/` at build time and exports typed accessors.

### Forms and validation

There are no forms. Frontmatter validation happens at build time via Zod in `lib/schema.ts`.

### Components

Grouped by role under `src/components/`. Design-system components are imported directly; local components exist only where the design system has no equivalent.

### Styling

Design-system tokens for colour, type, spacing and radius. No hard-coded values where a token exists. The page must be legible on a second screen in a dark room, so respect the design system's dark theme if it has one.

### Accessibility

Search and filters are real form controls with labels. Expanding an entry is a button with `aria-expanded`. Jump links move focus, not just scroll position. Full keyboard operation is a requirement, not a nice-to-have — see `docs/quality.md`.

---

## 5. Backend architecture

Not applicable. See section 1.

---

## 6. Data architecture

### Core entities

- **Trick** — one mixing problem and its fix. 100 of them.
- **Category** — one of ten groups. Holds a slug, a label, an order, and the short routine that opens the group.

### Trick fields

| Field | Type | Required | Notes |
|---|---|---|---|
| `id` | string | yes | Stable, never reused. Format `a-03`: group letter, dash, position in group |
| `number` | integer | yes | 1–100, global order, default sort |
| `title` | string | yes | The problem, phrased as the source document phrases it |
| `category` | string | yes | Slug matching a key in `categories.json` |
| `devices` | string[] | yes | May be empty. Allowed values below |
| `instruments` | string[] | no | Controlled vocabulary. Empty in v1 — reserved, see below |
| `genres` | string[] | no | Controlled vocabulary. Empty in v1 — reserved, see below |
| `tags` | string[] | no | Free-form keywords for search weighting |
| `summary` | string | yes | One line, the fix in plain words |

The body is markdown with three `###` headings in fixed order: Why, Try this, Watch for.

### Reserved fields — instruments and genres

The ten categories are stages of a mix: low end, clarity, vocals, and so on. Instrument and genre cut across all ten — an 808 problem is a low-end problem, and funk changes how you compress without becoming its own stage.

So they are not categories. They are defined now as optional arrays with controlled vocabularies, left empty for v1, on the assumption that a later pass annotates existing entries rather than adding new ones. Defining them now costs nothing and keeps that pass a matter of filling blanks instead of migrating a hundred files.

Two rules for whoever fills them in:

- Both are closed lists, declared in `lib/schema.ts` alongside the device slugs. A free-form string field would end up holding `hiphop` and `hip-hop` in the same dataset, which is exactly what `tags` is already for.
- An entry only gets a genre when the genre changes the answer. Tagging every compression entry with every genre Antonio likes makes the field worthless as a filter.

### Allowed values

Category slugs, in order: `low-end`, `clarity`, `vocals`, `drums`, `compression`, `space`, `stereo`, `levels`, `monitoring`, `digital`.

Device slugs: `channel-eq`, `compressor`, `ott`, `utility`, `send-return`, `none`. `none` is used for tricks about listening, arrangement or workflow rather than a device, so the filter can offer a meaningful "no device" option instead of showing blanks.

### File naming

`content/tricks/003-bass-and-kick-fighting.md` — zero-padded global number, then a slug, so files sort in reading order.

### Data ownership

Content is owned by the markdown files. Nothing else writes them. Favourites are owned by the browser and exist only on one device.

---

## 7. API conventions

Not applicable. No API.

---

## 8. Design system integration

### Tokens

Consumed from `@amezquita/design-system`. Local CSS references tokens; it does not redefine them.

### Components

Imported from the package. The package was made fully portable in v0.1.3, so a consuming app should not need local shim files re-exporting its internals. If it does, that is a bug in the package, not something to work around here.

### Variants and theming

Whatever the package provides. This project does not introduce a theme of its own.

---

## 9. Code conventions

### Naming

- files: kebab-case
- components: PascalCase
- hooks: `useThing`
- utilities: camelCase
- types: PascalCase, defined next to what they describe

### Type safety

Strict TypeScript. Content types are derived from the Zod schemas rather than declared twice.

### Error handling

At build time, throw. A malformed content file should stop the build with a message naming the file. At runtime, the only failure mode worth handling is local storage being unavailable or malformed, which degrades to an empty favourites list.

### Comments

Explain why, not what. The split script's assertions deserve comments; a filter function does not.

---

## 10. Testing strategy

### Unit tests

The content layer and the split script. Both are places where a silent error costs a hundred manual fixes.

### Integration tests

Not required for v1.

### End-to-end tests

Not required for v1.

### Accessibility testing

Manual keyboard pass before deploying, per `docs/quality.md`.

---

## 11. Security and privacy

No accounts, no personal data, no secrets, no user input that reaches a server. Local storage holds a list of trick ids and nothing else.

---

## 12. Performance

### Targets

- Search feels instant while typing, with all 100 entries in the DOM
- Fast initial load on a laptop sharing resources with a running DAW

### Preferred practices

- Static HTML with no runtime fetching
- Filtering by toggling visibility rather than re-rendering the full list
- No images or audio in v1

### Avoid

- Client-side search index libraries. 100 entries do not need one.
- Animating the expand behaviour in a way that costs frames while a DAW is running

---

## 13. Observability

None. No analytics, no logging, no error reporting. This is deliberate and listed as out of scope in `docs/product-north-star.md`.

---

## 14. Deployment and environments

### Environments

- local
- Vercel preview, per branch
- production, from `main`

### Environment variables

None expected. If one becomes necessary, that needs an ADR.

### Deployment process

Push to `main`; Vercel builds and deploys. A failing build blocks the deploy, which is the point of validating content at build time.

### Rollback strategy

Redeploy a previous Vercel build.

---

## 15. Preferred patterns

- Parse and validate at the edge of the system, then pass typed data inward
- URL as the source of truth for shareable state
- Derive types from schemas rather than maintaining both

## 16. Patterns to avoid

- Content embedded in components
- A client-side data layer for data that never changes after build
- Reaching for a library where twenty lines would do

---

## 17. Open architectural questions

- Whether the split script stays in the repo after it has run once, or is deleted as one-off tooling
- Whether favourites should eventually move to a URL-encoded shareable format rather than local storage
