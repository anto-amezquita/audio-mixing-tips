# source/

Original content, as written, before any processing.

## `mixing-tricks-library.md`

The 100 mixing tricks. Ten groups, A–J, ten entries each, plus a closing
"What's next for this library" section. Every entry has the same three
subheadings: Why, Try this, Watch for.

This is the project's one durable asset and the reason the repo still exists —
see `decisions/0004-park-the-site-build.md`. With the site build parked, this
file is not an input to a pipeline; it is the thing itself, read in an editor
with find-in-file.

Expected after copying, worth checking once:

- 963 lines
- 11 `##` headings — ten groups plus "What's next for this library"
- 100 headings matching `### <number>.`
- first entry `### 1. Kick and bass fight for the same space`
- last entry `### 100. Not checking the final bounce`

Verify from the repo root with:

```sh
wc -l source/mixing-tricks-library.md
grep -c '^## ' source/mixing-tricks-library.md
grep -cE '^### [0-9]+\.' source/mixing-tricks-library.md
```

On provenance: these entries were written by an AI assistant on 2026-09-29 with
no sources consulted and no citations recorded.
`decisions/0003-content-provenance.md` sorts the claims into three tiers and
says how each gets verified. Read it before treating anything here as settled —
in particular the statements about where things sit in Ableton Live Intro's UI,
which were written from memory and are the most likely to be simply wrong.

## `mixing-pain-points-100.md`

The problem list the tricks answer, written first. Optional — the library
stands on its own — but it is the only record of how the hundred were chosen,
and the two are numbered in parallel.
