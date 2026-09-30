# Ableton Live template — current state

Last updated: 2026-09-30
Edition: **Ableton Live Intro** (device availability is constrained by this — see Notes)
Set name: `amez`

This is a record of what the template contains, so future changes start from a known
state rather than from memory. It is descriptive, not prescriptive.

---

## 1. Global settings

| Setting | Value |
|---|---|
| Tempo | 100.00 BPM |
| Time signature | 4 / 4 |
| Key | C Major |
| Groove pool | Swing 16ths 66 loaded, Global Amount 0% |
| Main fader | 0.0 dB (unity) |

The tempo is a placeholder — the TEMPO track carries a note reading
"BPM: Choose your own".

---

## 2. Track layout

| # | Track | Type | Fader | Purpose |
|---|---|---|---|---|
| 1 | TEMPO | Audio (Ext. In 2) | 0.0 | Tempo reference / note |
| 2 | CLICK | MIDI | 0.0 | Metronome source |
| 3 | GUIDE | MIDI | 0.0 | Guide part |
| 4 | MARKERS | MIDI → No Output | — | Section labels only |
| 5 | ORIGINAL TRACK | Audio (Ext. In 1) | 0.0 | Reference / original demo |
| 6 | DRUMS | Group | **-10.0** | Contains 7–9 |
| 7 | Kick | Audio | 0.0 | |
| 8 | Snare | Audio | 0.0 | |
| 9 | Hi-hat | Audio | 0.0 | |
| 10 | BASS | Audio (Ext. In 1) | **-10.0** | |
| 11 | KEYS | MIDI (All Ins) | **-10.0** | |
| 12 | GUITAR | Audio (Ext. In 1) | **-10.0** | |
| 13 | VOCAL 1 | Audio (Ext. In 1) | **-10.0** | |
| A | Reverb | Return | 0.0 | Shared reverb, Post |
| B | Delay | Return | 0.0 | Shared delay, Post |
| — | Main | Main | **0.0** | |

### Why the instrument tracks sit at -10

Three reasons, in order of weight:

1. **Tracks sum at Main.** Each doubling of sources adds roughly 3 dB. Five tracks at
   unity clip the output before the arrangement is full.
2. **Room to move up.** If the loudest element is already at the ceiling, every mix
   decision becomes "what do I turn down?"
3. **Consistent input to the rack.** Compressor and OTT have fixed thresholds and react
   to level, so a consistent starting point makes the rack behave predictably.

Note the correction: low faders do **not** prevent internal distortion. Live's engine is
floating point and does not clip when summing past 0 internally. The clipping that is
real happens at the **Main output**, on the way to the interface or into a bounce.

The **-10 faders have nothing to do with recorded level.** The fader is post-record.
Take level is set at the interface input gain.

---

## 3. Arrangement markers

Locators 1–10, with section names laid out across roughly two minutes:

`INTRO` → `VERSE 1` → `PRE-CHORUS` → `CHORUS 1` → `VERSE 2` → `PRE-CHORUS` →
`CHORUS` → `BRIDGE` → `LAST CHORUS`

These exist so a demo starts with a song shape already on the timeline rather than an
empty grid.

---

## 4. The FX rack

An Audio Effect Rack saved as **`Amez FX Rack Template.adg`**, set as **Default Audio
Track** and **Default MIDI Track**, and present on tracks 6–13.

Device order:

```
Channel EQ → Compressor → OTT (Xfer, VST3) → Utility
```

**Bypassed by default.** It is there to be switched on when needed, not to process
anything on arrival.

Substitutions forced by Intro: Glue Compressor and EQ Eight are unavailable, so
Compressor and Channel EQ stand in for them.

OTT is Xfer's free plugin, v1.37.

---

## 5. Return tracks

Both returns are set to **Post**. Both devices are at **Dry/Wet 100%** — the return
carries only the effect, since the dry signal already reaches Main through the track
itself. Anything below 100% sends the dry signal twice.

Amount is controlled per-track with the **Sends A / B** knobs.

### A — Reverb

Ableton's Reverb at its default preset. Not yet tuned against real audio.

### B — Delay

Ableton's Delay at its default: Left and Right both synced to **3** at 1/16 division,
Feedback 21%, Dry/Wet 100%.

Two settings deliberately left at default until there is audio to judge them against:

- **Ping Pong is off.** Turning it on bounces repeats left–right — useful width on
  guitar and vocal ad-libs.
- **Filter is off.** Enabling it and rolling off the lows keeps repeats out of the
  low-mids.

---

## 6. Recording chain

Interface: **Focusrite** — exact model and generation not yet confirmed.

Input level is set with the gain knob on the interface. On Focusrite Scarlett units the
halo ring around the gain knob is the meter: green is good, red is clipping. Target is
roughly **-18 to -12 dBFS** at the input.

*Unverified:* the -18 to -12 target is standard practice for 24-bit recording, but has
not been checked against Focusrite's own documentation. Confirm the model before
relying on the halo-ring description.

---

## 7. Deliberately not included

These come from a widely-shared Ableton template walkthrough (a UK bass producer's
Suite template) and were considered and rejected:

- **Limiter chains** (sub limiter, basic limiter, top limiter, blank limiter) — these
  are limiters, and limiters exist to make things loud without clipping. That is a
  mastering-stage concern for club music. A demo does not need to be loud. The useful
  part underneath — treating bass as one thing and drums as another — is already
  available: the BASS track *is* the bass bus, and processing goes in the rack that is
  already on it.
- **Chain capture and premaster group** — same reasoning, plus the devices do not exist
  in Intro.
- **His instrument groups** — those reflect his sounds, not the instruments actually
  played here.

---

## 8. Open items

- Reverb and Delay settings are Ableton defaults, not yet tuned against a real take.
- No saved starting points ("shapes") per track type — bass, drums, keys, guitar,
  vocal. Parked deliberately: a saved setting only transfers when the source is
  predictable, and recorded sources are not. Revisit once there are logged sessions
  to learn from.
- Whether to save this as Live's global default Set.

---

## Related

- `source/mixing-tricks-library.md` — 100 mixing entries written against this exact
  rack (Channel EQ, Compressor, OTT, Utility). See `decisions/0003-content-provenance.md`
  for what in that library is verified and what is not.
