# product-north-star.md

## Purpose

This file defines what the product is, who it serves, why it exists, and the principles that should guide product decisions over time.

It is the stable reference point for the product. When features, designs, or technical choices compete, this document should help decide what deserves to exist and what does not.

---

## 1. Product summary

### Product name

Audio Mixing Tips

### One-line description

A searchable reference of 100 concrete mixing problems and their fixes, written for people mixing their own music in Ableton Live Intro.

### Longer description

Most mixing advice is either too abstract to act on or assumes a full studio plugin collection. This is a library of 100 specific problems — a muddy low end, a vocal that disappears in the chorus, a mix that falls apart on a phone — each with a short explanation of why it happens, concrete steps to try, and what to watch out for.

Every trick is written against four devices available in Ableton Live Intro: Channel EQ, Compressor, OTT and Utility. That constraint is the point. Somebody with the cheapest version of Live can act on every entry without buying anything.

The site is a single page with instant search and filters, designed to sit open on a second screen during an actual mixing session.

---

## 2. Problem

### The problem we solve

People learning to mix know something is wrong with their track but can't name it, and the advice they find either doesn't match the tools they own or stops at the level of "use EQ to clean it up."

### Who experiences it

Self-taught producers mixing their own music, usually solo, usually on entry-level software. They have no engineer to ask and no one to tell them whether what they're hearing is normal.

### Why it matters

Without a way to name the problem, every mix is guesswork repeated from scratch. Time goes into moving faders rather than into learning, and the same mistakes repeat across years of tracks.

---

## 3. Audience

### Primary users

- Antonio, mixing his own tracks in Ableton Live Intro
- Self-taught producers on entry-level DAW versions

### Secondary users

- Producers on Live Standard or Suite who want the same problem-first structure
- People learning mixing theory who want concrete examples

### Users are trying to

- Name a problem they can hear but can't describe
- Find a fix they can perform with the devices they actually own
- Learn why a problem happens, not just which knob to turn
- Return to a trick they found useful before

### Users should feel

- Capable, rather than under-equipped
- Oriented, rather than overwhelmed by options
- Trusted with the reasoning, not just the instruction

---

## 4. Value proposition

### We help users

Go from "something sounds wrong" to a specific fix they can perform in the next five minutes, with enough explanation that the next occurrence is recognisable without looking it up.

### Compared with alternatives

Video tutorials require watching linearly to find one answer. Forum threads are unstructured and contradictory. Most written guides assume plugins the reader doesn't own. This is searchable, filterable by the device in front of you, and deliberately scoped to the free tier of one DAW.

---

## 5. Product principles

#### 1. Problem first, device second

Entries are named after what the user hears, not after the tool. Someone searching "muddy" should land on the right entry without knowing that the answer involves EQ.

#### 2. Actionable within the session

Every entry includes concrete starting values — frequencies, ratios, times — so the user can act immediately rather than deriving settings from theory.

#### 3. Honest about constraints

Where Live Intro can't do something, say so and give the workaround, rather than pretending the limitation doesn't exist.

#### 4. Fast enough to use while working

The page is open next to a DAW during a session. Search must be instant and nothing should require a page load.

#### 5. Explain the why

Each entry says why the problem happens. A user who understands the cause stops needing the entry.

---

## 6. What this product should become

- The first place Antonio looks when a mix isn't working
- A reference someone can hand to a beginner without caveats
- A structure that could hold more content — other DAWs, other tiers — without redesign

---

## 7. What this product should not become

- A general music-production blog
- A tutorial site with video, courses, or a content calendar
- A social platform with accounts, comments, or ratings
- A tool that requires a login to be useful

---

## 8. Business and product goals

### Business goals

- Serve as a working portfolio piece demonstrating content architecture and design-system reuse
- Stay free to host and near-free to maintain

### Product goals

- All 100 entries findable in under ten seconds
- Usable on a second screen without adjusting anything

### Success signals

- Antonio uses it during real mixing sessions rather than reverting to notes
- A specific entry can be found by describing the symptom, not the fix
- Adding a new entry takes editing one markdown file and nothing else

---

## 9. Strategic scope

### In scope

- The 100 existing tricks, in ten categories
- Search, category filtering, device filtering, favourites
- Static hosting, no backend

### Out of scope

- User accounts and cross-device sync
- A CMS or admin interface
- Audio examples, images, video
- Comments, ratings, user-submitted content
- Analytics

---

## 10. Decision filter

When making product decisions, ask:

- Does this help someone find or act on a fix faster?
- Does it still work with Live Intro's device set?
- Does it work while the user is mid-session with a DAW open?
- Does it survive going from personal tool to public resource unchanged?
- Does it add anything that needs maintaining?

---

## 11. Open questions

- A guided "start here" path, walking the ten category routines in signal-flow order, would serve someone who can't yet name what's wrong. Deferred for v1 because the only user already knows his own problems. Revisit if this goes public.
- Should entries link to related entries, given several tricks genuinely depend on others?
- Does a printable one-page cheat sheet earn its place, or does search make it redundant?
- If this goes public, does device filtering need to cover Live Standard and Suite devices?
- Several entries reference Live's interface from memory rather than verified fact. Which need checking in Live before this is published?
