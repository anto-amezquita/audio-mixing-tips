# CLAUDE.md

This repo's instructions for AI agents live in [AGENTS.md](AGENTS.md). Read that first — it holds the reading order, the skills manifest, and the rules for making changes here.

Everything below is specific to Claude Code and does not duplicate AGENTS.md.

## Before starting work

Read `docs/backlog.md` first. It is the only document here that changes turn to turn, and it tells you whether there is open work already in flight. If an item is marked blocked, do not start the thing it is blocked on.

## Things that will bite you in this repo

- **`docs/brand.md`, `docs/design.md` and `docs/content.md` are unfilled kit templates.** AGENTS.md lists them in its reading order. Read them if you like, but do not treat their placeholder text as product direction. The real product direction is in `docs/product-north-star.md`, `docs/architecture.md` and the spec in `/specs`.
- **`docs/quality.md` is also still a template**, and both the architecture and the spec reference it as the source of truth for the accessibility pass. Ask before relying on it.
- **`@amezquita/design-system` is a hard dependency.** Phase 1 of the implementation plan exists to prove it resolves and renders. If it does not, stop and say so rather than building local substitutes.
- **`source/mixing-tricks-library.md` may not be present yet.** It is a manual copy step tracked in the backlog. Without it, `scripts/split-library.ts` has nothing to split. Do not generate placeholder content to work around this.
- **Content is never written by hand into components or constants.** See `docs/architecture.md`, section 2.

## Commands

The repo is not scaffolded yet. Once it is, `package.json` is the source of truth. Do not run environment-changing commands before then without asking.
