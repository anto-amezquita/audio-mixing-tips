# 0003 — Content provenance and how claims get verified

## Status

Accepted

## Context

The 100 tricks in `source/mixing-tricks-library.md` were written by an AI assistant in a chat session on 2026-09-29. No sources were consulted and no citations were recorded. The content is synthesis from training data — it reflects widely repeated mixing practice, but no individual entry can be traced to a book, an engineer, or a measurement. There is no provenance to recover, because none was ever captured.

That sits awkwardly against principle 3 of `docs/product-north-star.md`, "honest about constraints", and it matters more than usual here because the product is a learning tool. A wrong claim doesn't cost one mix; it installs a habit that later has to be unlearned.

The claims are not uniformly risky. They fall into three tiers:

- **Physics.** Mechanically true and independently checkable. Two sources occupying the same frequency range mask each other. Summing correlated signals out of phase cancels. These need no citation.
- **Convention.** Practice that working engineers broadly share, but which is taste-dependent and in places contested. High-pass everything that isn't bass; compress the bus gently. Defensible, not universal.
- **Unverified interface claims.** Statements about where something sits in Ableton Live Intro's UI — the Options menu location for delay compensation, A/B automation shortcuts, track delay, oversampling on distortion devices. These were explicitly flagged "from memory" when written. They are specific, falsifiable, and the most likely to be simply wrong.

## Decision

Verification is tiered to match, rather than applying one standard to all 100 entries.

**Physics claims** need no external source. If a claim is mechanically true it stands on its own.

**Convention claims** are checked against a small fixed set of reference texts:

- Mike Senior, *Mixing Secrets for the Small Studio* (Sound On Sound, 3rd edition). Primary reference. Written for modest gear in untreated rooms, which is this project's exact situation, and its claims are drawn from interviews with over 160 named engineers.
- Bobby Owsinski, *The Mixing Engineer's Handbook*. Secondary. Interview-structured, so it is useful for telling a universal practice apart from one school's habit.
- Roey Izhaki, *Mixing Audio*, if a physics-tier claim ever does need backing.

All three are mainstream and rock/pop-leaning. A search for genre-specific equivalents covering funk, acid jazz and hip-hop found none of comparable standing — what exists is blog posts and plugin-vendor marketing, not reference texts. Genre claims are therefore verified by case study and by ear rather than by book:

- **Sound On Sound, *Inside Track: Secrets Of The Mix Engineers*** (soundonsound.com/mix-secrets). Monthly since 2007. Each article covers one named engineer mixing one named hit record, and the back catalogue runs deep in hip-hop, R&B and soul — Dave Pensado, Jaycen Joshua, Tom Elmhirst on Amy Winehouse's "Rehab". Closer to a primary source than any book: it records what someone actually did on a record that exists, rather than what is generally advisable.
- **Reference tracks.** For genre, the record beats the text. Whether a funk low end is right gets settled by A/B-ing against a funk record on the same monitors, not by reading a chapter. Genre annotations should name a reference track wherever one makes the point.

**Interface claims** are verified in Ableton Live Intro itself, by opening the menu. A book cannot settle these and neither can a search.

Where a convention claim turns out to be contested rather than settled, the entry says so instead of picking a side silently.

A `confidence` field in the frontmatter was considered and **deferred**. It would record which tier an entry sits in, but designing the field before the verification pass has run means designing it twice — the pass will show what actually needs recording. Revisit once the pass is done.

## Alternatives considered

- **Re-derive the whole library from sources.** Discard the current 100 and rewrite each entry with a citation attached. Most rigorous. Rejected as disproportionate: it discards content that is probably fine to fix content that is probably wrong, and the physics tier gains nothing from a citation.
- **Cite everything, including the physics.** Uniform and simple to explain. Rejected because it spends the same effort on "two sounds in the same range mask each other" as on a contested compression claim, and citation clutter on self-evident statements trains the reader to ignore citations.
- **Add the `confidence` field now.** Cheap while the schema is still being edited. Rejected for sequencing, not cost — see above.
- **Ship as is and fix what breaks.** Defensible for a personal tool. Rejected because the failure mode is silent: an unverified claim that sounds plausible gets practised for months before anything reveals it was wrong.
- **Verify by ear alone, no reference texts.** Slowest, and the only method that genuinely teaches. Kept for the interface tier, where it is the only option, but rejected as the sole method for convention claims — ears confirm that something sounds different, not that it is standard practice.

## Consequences

### Positive

- The riskiest claims get the cheapest check. Verifying the interface tier needs a keyboard and an afternoon, not a library.
- Two named reference texts give the convention tier something to argue with, which is most of what "trustworthy" means at this stage.
- The tiering is reusable: any entry added later gets sorted into one of the three and handled accordingly.
- The honesty principle is satisfied by disclosure even before the pass is complete. The library can say what it is.

### Negative

- The library still cannot cite a source per entry, and will not after this pass. It records that a claim was checked, not where it came from.
- The book base is narrow and rock/pop-leaning. *Inside Track* and reference tracks cover the genre gap unevenly: the series is strong on hip-hop, R&B and soul, thin on acid jazz, and it documents individual records rather than stating general principles — which means reading several articles to find a pattern a book would have stated outright.
- Reference-track comparison is only as good as the monitoring, which in an untreated room is the weakest link in the setup. Category I of the library covers exactly this, and it has not been verified either.
- The verification pass is unscheduled work against 100 entries and will not happen in one sitting.
- Until the pass runs, every entry carries the same apparent authority regardless of tier, because nothing in the content distinguishes them. That is the gap the deferred `confidence` field would close.

## Related files

- `docs/product-north-star.md` — principle 3, honest about constraints
- `docs/backlog.md` — the Live Intro verification item
- `docs/architecture.md` — section 6, where `confidence` would be added
- `source/mixing-tricks-library.md`
