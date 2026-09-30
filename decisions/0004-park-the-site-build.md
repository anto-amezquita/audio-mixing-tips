# 0004 — Park the site build

## Status

Accepted — 2026-09-30

## Context

The project was set up to turn the 100-entry mixing library into a searchable Next.js site on Vercel: live client-side search, filters by category and device, favourites in local storage. Phases 1–5 are specified in `specs/2026-09-29-mixing-tips-reference.md` and none of them have been built.

Revisiting the original goal made the mismatch clear. The point was to learn to use one Audio Effect Rack — Channel EQ, Compressor, OTT, Utility — well enough to mix demos and finished tracks as an independent musician. A searchable reference serves a different need: fast retrieval of one entry out of a hundred, by someone who already knows the material. That is a mid-mix need, not a learning need.

Two things follow. First, at four devices, search has little to do — the question is nearly always about something already on screen. Second, the retrieval problem the site would solve is already solved well enough: the library is a markdown file, and an editor with find-in-file covers it for zero work.

Against that sits the cost. The build is weeks of Next.js, and it is work that resembles progress on music without being any. The stated priority is writing and making music.

## Decision

Stop the build. No Phase 1, no scaffold, no deployment.

The library is used as a markdown file, open in an editor on a second monitor, searched with find-in-file.

Everything already decided stays in the repo unchanged: the spec, ADRs 0001–0003, the schema in `docs/architecture.md`, and the backlog. Parking is not deleting. If a genuine mid-mix retrieval need shows up later — reaching for the file often enough that find-in-file starts to chafe — the thinking is intact and the build can start from where it stopped.

## Alternatives considered

- **Build Phase 1 only, to see.** Cheap and bounded. Rejected because a scaffold with nothing in it answers no question worth asking, and a half-built repo invites finishing itself.
- **Build a smaller version — one page, no filters, no favourites.** Closer to proportionate. Rejected on the same ground as the full build: even a small site solves retrieval, and retrieval is not the problem.
- **Delete the repo.** Honest about the odds of returning. Rejected because the content and the decisions cost real effort and the repo is nearly free to keep.
- **Keep building and treat it as a portfolio piece.** Defensible — it would demonstrate the design system in use. Rejected because that is a different project with a different brief, and pretending it is this one is how the mismatch happened in the first place.

## Consequences

### Positive

- The time goes to music, which is the actual goal.
- The library becomes usable today rather than after a build.
- Learning the rack happens on real tracks, one device at a time, which is how it was going to have to happen regardless of where the text was displayed.
- The verification work in ADR 0003 is unaffected. It applies to the content, not the site, and is arguably more useful now — the file is the product.

### Negative

- Retrieval stays worse than the site would have made it. Find-in-file will not match on concepts the entry does not name, so some entries stay effectively unfindable until read end to end.
- No favourites, no filtering by device, no annotation layer for instruments and genres. The schema fields exist and stay empty, with nothing to render them.
- `@amezquita/design-system` goes unexercised on this project.
- The longer the repo sits, the more the spec dates — the design system will move, Next.js will move, and resuming means re-checking assumptions rather than picking up cleanly.

## Related files

- `specs/2026-09-29-mixing-tips-reference.md` — the build that is now parked
- `decisions/0003-content-provenance.md` — content verification, still live
- `docs/backlog.md` — open items, now marked parked
- `source/mixing-tricks-library.md` — **not yet in the repo**; see the backlog
