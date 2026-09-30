# backlog.md

## Purpose

This file holds the product's live, open work — nothing else. Every other file in `docs/` is stable reference (what the product is, how it's built, what quality means); this one is the only file expected to change from session to session.

Its job is narrow on purpose: a session should be able to open this file and know what's actually actionable right now, without paging through `product-north-star.md` or a pile of closed specs to find it.

---

## 1. Session protocol

1. Read this file first, before the other `docs/` files — it's the one that tells you whether there's open work waiting, and the other docs are read for context on *how* to do it, not *what* to do.
2. If it's empty, there's no open backlog item. Check with whoever's directing the work before starting something new.
3. Pick an item, or ask if more than one is open and it's not obvious which.
4. When an item ships or a decision is made: remove it from this file. If it's substantial enough to need a record, write a spec in `/specs` or an ADR in `/decisions` per this repo's own conventions — this file holds only what's still open, never history.
5. If new backlog work surfaces mid-session (a deferred fix, a follow-up idea, something explicitly punted on), add it here before finishing — not just in memory or a chat transcript.

---

## 2. Open items

> **Parked 2026-09-30 — see `decisions/0004-park-the-site-build.md`.** The site build is stopped; the library is used as a markdown file instead. Nothing below is being worked on. The first item is still worth doing on its own merits, because it is the only thing standing between the content and a durable home. The rest is preserved for a possible return, not queued.

### Commit the source library to `source/mixing-tricks-library.md`

- **Source:** The 100 tricks were written in a chat session and exist as a published artifact, not as a file in this repo.
- **Why it matters:** The content only exists as a chat artifact. That was a build blocker; with the build parked it is now a preservation problem, which is worse — the library is the one thing from this project that has standing value, and it does not currently live in the repo at all.
- **Status:** Not started, and the only item still worth doing now. Download from https://claude.ai/artifact/1yazc49viGjfPJtSgLG1ZX (roughly 960 lines, 58 KB), save as `source/mixing-tricks-library.md`, commit. Verify ten `##` group headings and 100 entries survived the copy before committing.

### Build the site, Phases 1–5

- **Source:** `specs/2026-09-29-mixing-tips-reference.md`, section 11.
- **Why it matters:** This is the product. Everything else in this file is either a prerequisite or a follow-up.
- **Status:** Parked with the build, per ADR 0004. Phase 1 was never started.

### Verify the Live Intro interface claims in the content

- **Source:** `docs/product-north-star.md` section 11; method set by `decisions/0003-content-provenance.md`.
- **Why it matters:** Several entries describe Live's UI from memory — where delay compensation sits in the Options menu, A/B automation shortcuts, track delay, oversampling on distortion devices. Principle 3 is "honest about constraints"; shipping an instruction that names a menu item that isn't there breaks it. This is the highest-risk tier of the three in ADR 0003 and the cheapest to check.
- **Status:** Not started. Needs a pass in Live with the content open — a book can't settle these. Can happen after the site is built; the fix is editing content files, not code.

### Verify the monitoring entries (group I) ahead of the rest

- **Source:** `decisions/0003-content-provenance.md`. Split out of the convention-tier item 2026-09-30.
- **Why it matters:** ADR 0003 verifies genre claims by A/B-ing against reference records. That method is only as good as the monitoring, so the ten monitoring entries decide whether every later ear-based check means anything. Verifying them last would mean running the whole pass on an instrument that hasn't been calibrated.
- **Status:** Not started, and small enough for one sitting — ten entries, not a hundred. Same method as the rest of the convention tier: Senior's *Mixing Secrets for the Small Studio* is unusually strong here, since it is written for untreated rooms. Do this before the other convention claims and before any genre annotation that names a reference track.

### Check the remaining convention-tier claims against the reference texts

- **Source:** `decisions/0003-content-provenance.md`.
- **Why it matters:** The library was written without sources. Physics-tier claims stand on their own and interface claims get verified in Live, but the contested middle — high-pass everything that isn't bass, how hard to hit the bus — is taste-dependent and is where a wrong claim quietly becomes a habit.
- **Status:** Not started, and unscheduled: it's a pass over roughly a hundred entries, not one sitting. Blocked in practice on the monitoring item above — not for tooling reasons, but because ear-based checks made on unverified monitoring have to be redone. References are Mike Senior's *Mixing Secrets for the Small Studio* (primary) and Bobby Owsinski's *The Mixing Engineer's Handbook* (secondary); for genre-specific claims, Sound On Sound's *Inside Track* series and reference tracks, per ADR 0003. Where a claim turns out contested rather than settled, say so in the entry instead of picking a side. Revisit the deferred `confidence` field once this has run — ADR 0003 deliberately left it undesigned until the pass shows what needs recording.

### Fill or delete the unused kit templates

- **Source:** Repo scaffolded from the AI Product Starter Kit; `docs/brand.md`, `docs/design.md`, `docs/content.md` and `docs/quality.md` are still template text.
- **Why it matters:** `docs/quality.md` is referenced by both the architecture and the spec as the source of truth for the accessibility pass, so it is load-bearing and empty. The other three may not earn their place on a project that inherits its entire visual layer from the design system.
- **Status:** Not started. Fill `quality.md`; decide on the other three rather than leaving template text in the repo. `CLAUDE.md` already warns agents not to treat their placeholder text as product direction, which buys time but is not a fix.

### Annotate entries with instruments and genres

- **Source:** `specs/2026-09-29-mixing-tips-reference.md` section 6, `docs/architecture.md` section 6. Decided 2026-09-30.
- **Why it matters:** The ten categories are stages of a mix, so nothing in the library is findable by instrument or by genre — a guitar problem and an 808 problem both live under "low end" with no way to tell them apart. Covering that by writing new genre-specific entries would abandon the small, solid starting set the library exists to be; annotating the existing hundred keeps it.
- **Status:** Deferred, deliberately. v1 defines `instruments` and `genres` in the schema and leaves every entry empty. The work when it happens: settle both vocabularies, then a pass over all 100 entries adding values only where the instrument or genre actually changes the advice. Genres to start from are pop, funk, nu-funk, acid jazz and hip-hop. Genre annotations should name a reference track where one makes the point, per ADR 0003 — which puts this after the monitoring item. UI comes after the annotation, not before — an empty filter is worse than no filter.

### Apply the filter-UX findings to the spec

- **Source:** Competitive and UX research, 2026-09-30.
- **Why it matters:** Three findings never made it into the spec. FR-13 requires a visible count but doesn't say where — research says it belongs beside the filter controls, not only in the header, so a user can see a filter's match count before committing to it. Device filter labels ("Channel EQ", "OTT") are jargon that would survive personal use but not a public version. Live filtering was confirmed correct at this size.
- **Status:** Not started. Decide whether to amend the spec now or handle the label question only if the site goes public.

---

## 3. What doesn't belong here

- **Finished work.** Once something ships, it leaves this file. History lives in `/specs` (what was built and why) and `/decisions` (architectural choices), not in a growing log here.
- **Vague aspirations.** "Improve performance" isn't an item; "investigate the N+1 query on the dashboard load" is. If it's too vague to hand to someone as a starting point, it's not ready for this file yet.
- **A roadmap with dates or phases.** This file tracks *what's open*, not a schedule. If the product needs date-based planning, that belongs in whatever project-management tool `docs/linear-workflow.md` (or its equivalent) points at — this file stays a plain list.

---

## Final review checklist

- Could someone open this file cold and know what to work on next?
- Is every item concrete enough to start, not just a topic?
- Has everything that shipped since the last review been removed?
- Does anything here actually belong in a spec or ADR instead, now that it's been thought through?
