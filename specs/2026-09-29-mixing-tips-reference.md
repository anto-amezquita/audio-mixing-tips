# Mixing tips reference — v1

## 1. Overview

### Summary

A single-page, searchable reference holding 100 mixing tricks, split out of one long source document into structured content files, rendered statically and filterable by category, device and favourites.

### Problem

The 100 tricks currently exist as one long markdown document. Finding the relevant entry mid-session means scrolling and reading, which is slow enough that the document doesn't get used during actual mixing. The content is good; the access is the problem.

### Intended users

Primary: Antonio, mixing in Ableton Live Intro with the page open on a second screen. Secondary: self-taught producers on entry-level DAW versions, if this becomes public.

### Desired outcome

Any of the 100 entries is findable in under ten seconds by describing the symptom, and the page is usable without leaving the DAW.

---

## 2. Goals and non-goals

### Goals

- All 100 tricks available as structured, individually editable content
- Instant client-side search across title, summary, tags and body
- Filtering by category and by device
- Favourites, so frequently used tricks are one click away
- Deployed and usable on a second screen

### Non-goals

- Accounts, authentication, cross-device sync
- A CMS or admin interface
- Comments, ratings, user-submitted content
- Audio examples or images
- Analytics
- Server-rendered or dynamically fetched content
- A guided "start here" path through the categories. Deliberately deferred, not rejected — see section 6 for the one structural constraint it places on v1.
- Browsing or filtering by instrument or by genre. Also deferred rather than rejected — the schema reserves the fields, v1 leaves them empty. See section 6.

### Success criteria

- 100 content files exist, all validating against the schema
- Searching a symptom word returns the relevant entry
- A filtered view can be bookmarked and restored from its URL
- Adding a new trick requires creating one markdown file and nothing else

---

## 3. User experience

### Primary user stories

- As someone mixing, I want to search a symptom I can hear so I can find the fix without knowing its name.
- As someone using one device, I want to filter to that device so I only see what applies right now.
- As a returning user, I want my starred tricks in one place so I don't search for the same thing repeatedly.
- As someone reading to learn, I want to browse a whole category in order so I get its routine and all ten entries together.

### Main user flows

**Search.** User types in the sticky search field. Entries not matching hide. Categories with no matches hide entirely, heading included. A count shows how many entries are visible.

**Filter.** User selects one or more categories, one or more devices, or toggles favourites-only. Filters combine. The query string updates. A "clear all" control appears whenever anything is active.

**Read.** Entries are collapsed by default, showing title, summary, device tags and a star. Clicking expands the body — Why, Try this, Watch for.

**Favourite.** Clicking the star adds or removes the entry's id from local storage. The favourites filter reads that list.

**Navigate.** Category jump links, sticky on desktop, collapsible on mobile, scroll to that category and move focus to its heading.

### States and edge cases

- **Default:** all 100 entries visible, collapsed, in global number order, grouped by category.
- **Empty (search):** no entry matches. Show a message naming the search term and a way to clear it. Do not show ten empty category headings.
- **Empty (favourites):** favourites filter active with nothing starred. Explain what starring does rather than showing a bare empty page.
- **Loading:** none. Content is in the HTML.
- **Error:** none at runtime. Content errors break the build instead.
- **Local storage unavailable or malformed:** treat as an empty favourites list. The page works; starring silently does nothing rather than throwing.
- **First visit vs returning:** identical, except that a returning visitor's stars are restored after mount.

### UX notes

The page is used on a second screen beside a DAW, often in a dark room. Readable line length, the design system's dark theme if it has one, and no animation that costs frames while Live is running. Focus lands on the search field at load.

---

## 4. Functional requirements

- `FR-01` The system renders all 100 tricks at build time, grouped into ten categories in defined order.
- `FR-02` Each category displays its label and its intro routine above its entries.
- `FR-03` Each entry displays title, summary, device tags, and a favourite toggle when collapsed.
- `FR-04` Clicking an entry expands it to show Why, Try this and Watch for.
- `FR-05` The user can search across title, summary, tags and body, weighted in that order.
- `FR-06` Search filters the visible entries as the user types, with no network request.
- `FR-07` A category section with no visible entries is hidden entirely, including its heading.
- `FR-08` The user can filter by one or more categories.
- `FR-09` The user can filter by one or more devices, including `none`.
- `FR-10` The user can toggle a favourites-only view.
- `FR-11` Search and all filters combine; active filters are reflected in the URL query string.
- `FR-12` A "clear all" control is visible whenever any search or filter is active.
- `FR-13` The interface shows a count of currently visible entries.
- `FR-14` Favourites persist in local storage under a single namespaced key.
- `FR-15` Category jump links scroll to a category and move keyboard focus to its heading.
- `FR-16` The build fails if any content file has invalid frontmatter.

---

## 5. Non-functional requirements

- **Performance:** search responds while typing with all 100 entries in the DOM. No client-side search index library.
- **Accessibility:** full keyboard operation, visible focus, labelled controls, `aria-expanded` on entry toggles. See `docs/quality.md`.
- **Responsive:** usable from a phone up to a second monitor. Jump links collapse on small screens.
- **Browser support:** current evergreen browsers. No IE, no polyfills.
- **SEO:** basic metadata and a sensible title. Not a priority for v1 but the content is static, so it comes nearly free.
- **Maintainability:** adding a trick means adding one markdown file.

---

## 6. Information architecture and data

### Data entities

**Trick** and **Category**, as defined in `docs/architecture.md` section 6. That section holds the field table, the allowed category and device slugs, and the file-naming convention; it is the source of truth and is not repeated here.

### Structural constraint — reserved instrument and genre fields

The ten categories are stages of a mix. Instrument and genre cut across all ten, so they are a layer over the existing hundred entries rather than a set of new ones — a later pass annotates what is already there.

For v1 this means only: `instruments` and `genres` exist in the frontmatter schema as optional arrays with closed vocabularies, and every entry leaves them empty. No UI, no filter, no content work. `docs/architecture.md` section 6 holds the field definitions and the two rules for filling them in later.

Do not fold these into `tags`. `tags` is free-form and exists for search weighting; these need controlled values because they will eventually drive filter controls.

### Structural constraint — deferred guided path

A guided "start here" path is out of scope for v1 (section 2), but it would be assembled from the ten category routines read in order. So each Category's `routine` stays a discrete field in `categories.json`, distinct from `label` and from any description text. Do not flatten a routine into prose that only makes sense under its own heading — write it so it still reads as a step when lifted out of the page and placed in a sequence. Honouring this keeps the path a later addition rather than a content rewrite.

### Relationships

Each Trick belongs to exactly one Category, by slug. Each Trick has zero or more devices. Categories own display order; tricks own their order within a category through `number`.

### Permissions

None. Everything is public and read-only.

### State changes

Content changes only through editing files in the repo. Favourites change through the star control and live only in the browser.

---

## 7. Technical approach

### Proposed architecture

Static Next.js site. `lib/content.ts` reads `content/tricks/` and `content/categories.json` at build time, validates each file against Zod schemas in `lib/schema.ts`, and exports typed accessors. The page component receives typed data and renders everything. Search and filtering run in the browser over data already present.

### Frontend responsibilities

Rendering, search, filtering, expand/collapse, URL synchronisation, local-storage favourites.

### Backend responsibilities

None.

### Reused systems

`@amezquita/design-system` for tokens and components. Import before building anything locally.

### New technical work

- `scripts/split-library.ts` — one-off, turns the source document into 100 content files plus `categories.json`
- `lib/schema.ts`, `lib/content.ts` — validation and typed access
- `lib/favourites.ts` — local-storage read/write with failure tolerance
- The page and its components

---

## 8. Interface and component breakdown

### SearchAndFilters (sticky header)

- **Purpose:** every control that changes what's visible, in one place that stays on screen
- **Inputs:** current query, active category and device filters, favourites toggle state, visible count, the category and device lists
- **Outputs:** change events for each control; "clear all"
- **States:** default; any filter active (clear-all visible); zero results
- **Responsive:** filters collapse behind a disclosure on small screens
- **Accessibility:** real labelled inputs; the visible count is announced politely on change; focus lands here at load

### CategoryNav

- **Purpose:** jump to a category without scrolling
- **Inputs:** categories, which are currently non-empty
- **Outputs:** navigation to a category heading
- **States:** default; a category hidden by filters is disabled or omitted
- **Responsive:** sticky sidebar on desktop, collapsible on mobile
- **Accessibility:** moves focus to the target heading, not just scroll position

### CategorySection

- **Purpose:** group ten entries under a heading and its routine
- **Inputs:** category, its visible tricks
- **States:** default; hidden entirely when no entries are visible

### TrickCard

- **Purpose:** one trick, collapsed or expanded
- **Inputs:** the trick, whether it's favourited, whether it's expanded
- **Outputs:** toggle expand, toggle favourite
- **States:** collapsed; expanded; favourited; focus and hover
- **Accessibility:** the toggle is a button with `aria-expanded`; the star is a button with a label that names the trick, not just "favourite"

---

## 9. Risks, trade-offs, assumptions, and open questions

### Risks

- The split script producing subtly wrong output. A bad split means 100 files to repair by hand. Mitigated by assertions — see acceptance criteria.
- Device tags inferred from body text being wrong often enough to make the device filter untrustworthy.

### Trade-offs

- **All entries in the DOM** — instant filtering, at the cost of a larger initial page. At 100 entries this is the right side of the trade.
- **Local-storage favourites** — no accounts and no backend, at the cost of favourites living on one device only.
- **No search index library** — less code and no dependency, at the cost of naive matching. Acceptable at this size.

### Assumptions

- `@amezquita/design-system` installs cleanly into a fresh Next.js app with no local shim files, as of v0.1.3.
- The source document's structure is regular enough to parse mechanically.
- The first sentence of each Try this section works as a `summary`. If it doesn't, summaries need a manual pass.

### Open questions

- Should entries cross-link to related entries?
- Does the split script stay in the repo after it has run?
- Do device tags need a confidence signal, or is a review list enough?

---

## 10. Acceptance criteria

- `content/tricks/` contains exactly 100 files, each validating against the schema
- Every `category` value matches a key in `categories.json`
- Every `id` and every `number` is unique across the 100 files
- Every body contains all three headings: Why, Try this, Watch for
- `next build` and `tsc` pass with no errors
- All 100 entries render on the page
- Search, category filter, device filter and favourites each work, and combine
- Active filters survive a page reload via the URL
- The full flow works by keyboard
- The site is deployed to Vercel and loads

---

## 11. Implementation plan

### Phase 1 — Foundations

Scaffold Next.js with TypeScript. Install `@amezquita/design-system`. Confirm a clean `next build` with one design-system component rendering. Stop here if the package doesn't resolve — everything downstream depends on it.

### Phase 2 — Content

Write `scripts/split-library.ts`, splitting `source/mixing-tricks-library.md` into `content/tricks/` and `content/categories.json`. Derive `id`, `number`, `category` and `title` from the document's structure, and `summary` from the first sentence of Try this. Infer `devices` from device names appearing in the body and write the best guess. Assert the acceptance criteria above before finishing; if an assertion fails, fix the script and re-run rather than hand-editing output. Output a review list of entries where no device was found or more than two were.

Then build `lib/schema.ts` and `lib/content.ts`, failing the build on invalid frontmatter.

### Phase 3 — Static page

Render all categories and entries with no interactivity. Verify all 100 appear and read correctly.

### Phase 4 — Interaction

Search, then filters, then expand/collapse, then jump links, then URL synchronisation. Favourites last, since it's the only piece touching persistence.

### Phase 5 — Validation and release

Keyboard pass, responsive check, `docs/quality.md` review, deploy to Vercel, and check it at the size it'll actually be used.
