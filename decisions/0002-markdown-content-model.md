# 0002 — One markdown file per trick, with validated frontmatter

## Status

Accepted

## Context

The 100 tricks exist as one long markdown document (`source/mixing-tricks-library.md`). Every entry has the same shape: a title, then three `###` sections in fixed order — Why, Try this, Watch for. Ten groups of ten, each group opening with a short routine.

That regularity means the content can be split mechanically. The question was what it should be split *into*: structured data, or prose files with structured headers.

The content is prose. It is read by a human mid-session, edited by hand, and its value is in the wording. Anything that turns paragraphs into quoted strings makes the editing worse to serve a machine that doesn't need it.

## Decision

One markdown file per trick in `content/tricks/`, named by zero-padded global number and slug. Frontmatter carries the structured fields — `id`, `number`, `title`, `category`, `devices`, `tags`, `summary`. The body stays markdown with the three fixed `###` headings.

Category metadata — slug, label, order, and the group's intro routine — lives in `content/categories.json`, because it is genuinely a small fixed lookup table rather than prose to edit.

Frontmatter is validated with Zod at build time in `src/lib/schema.ts`. Invalid frontmatter fails `next build`. A typo in a category slug must stop the build, never silently drop an entry out of a filter.

`scripts/split-library.ts` performs the split once, asserting the acceptance criteria in section 10 of the spec before it finishes.

## Alternatives considered

- **A single JSON or YAML file holding all 100 entries.** Compact and trivially loadable. Rejected because editing a paragraph means editing a quoted string with escaped newlines, merge conflicts hit one file for every change, and the diff for a one-word fix is unreadable.
- **Keeping the source document whole and parsing it at build time.** No split script, no 100 files, and one place to edit. Rejected because it leaves the document as the unit of change: adding an entry means finding the right spot in a 960-line file, and the parser becomes load-bearing forever rather than running once. It also makes per-entry metadata awkward — where would `tags` live?
- **A headless CMS.** Rejected outright. It adds a service, an account and a network dependency to content that changes rarely and is authored by one person who already writes markdown.
- **MDX.** Would allow components inside entries. Rejected as unearned — no entry needs a component, and section 12 of `docs/architecture.md` rules out images and audio for v1.

## Consequences

### Positive

- Adding a trick is creating one file. That is the maintainability success criterion in section 2 of the spec.
- Diffs are readable and scoped to the entry that changed.
- Build-time validation means the device and category filters can be trusted: a bad slug can't reach production.
- Content stays portable. Markdown with frontmatter survives a move to a different framework.

### Negative

- 100 files in one directory. Navigable because of the naming convention, but it is a lot of files for a beginner opening the repo.
- The split script is a single point of failure. A subtly wrong split means 100 files to repair by hand — mitigated by assertions, and by fixing the script and re-running rather than hand-editing its output.
- Frontmatter is duplicated structure: the same field list lives in the schema and in every file. The Zod schema is the single source of truth for the types, which limits the damage.
- `devices` is inferred by the script from device names appearing in body text. Some guesses will be wrong. The script outputs a review list for entries where it found none or more than two.

## Related files

- `docs/architecture.md` — section 6, the canonical field table and allowed slugs
- `specs/2026-09-29-mixing-tips-reference.md` — sections 6, 9 and 11
- `scripts/split-library.ts`
- `src/lib/schema.ts`, `src/lib/content.ts`
