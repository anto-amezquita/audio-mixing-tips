# 100 Mixing Pain Points (and What To Try)

A working library for building your mixing skills in Ableton Live Intro, using the devices in your FX rack: **Channel EQ, Compressor, OTT, Utility**. It comes from a broad read of mixing guides, forum threads and engineering articles (sources at the bottom).

**How to read it.** Every number here is a starting point taken from those sources, and the sources sometimes disagree. Treat them as places to begin, then trust your ears. Each entry can grow into its own page later, with settings for your rack.

---

## Start here: the six habits that fix the most

1. **Balance with faders and panning before touching any plugin.** Many "plugin problems" are level problems.
2. **High-pass everything that doesn't need low end.** Channel EQ has a high-pass switch.
3. **Check in mono.** Utility has a Mono button. If something disappears, you have a phase or width problem.
4. **Compress lightly, and level-match before judging.** Louder always sounds better, so match volume first.
5. **Leave headroom.** Aim for mix peaks around -6 dBFS.
6. **Compare against a reference track at the same volume, and listen quietly sometimes.**

---

## A. Low end (1-10)

1. **Kick and bass fight for the same space.** Give each its own zone (kick weight vs bass body), sidechain the bass to the kick, and judge the balance in mono.
2. **Low-mid mud (roughly 200-500 Hz).** Many tracks stack energy here. Find which ones contribute and cut gently with Channel EQ instead of cutting the same range everywhere.
3. **Rumble nobody can hear.** Inaudible low content on non-bass tracks eats headroom. Switch on Channel EQ's high-pass on anything that doesn't need lows.
4. **Kick is loud but has no punch.** Make sure the click or attack is audible. A bass that masks it, or a compressor attack that's too fast, can hide it.
5. **Wide bass, sloppy low end.** Keep lows centered. Utility's Bass Mono makes everything below its set frequency mono; sources suggest somewhere around 100-150 Hz.
6. **Kick and bass phase cancellation.** The low end vanishes in mono. Press Utility's Mono, then try the phase-invert (Ø) button on one of the two.
7. **Long 808 or sub tails overlap.** End notes before the next hit so low notes don't smear.
8. **Too much sub energy.** Extra sub triggers the limiter early and stops the mix from getting loud. Trim what you can't hear.
9. **Bass vanishes on phone and laptop speakers.** Small speakers can't reproduce sub. Give the bass upper harmonics (saturation or a layer) so it stays audible.
10. **Reverb and delay carry low end.** High-pass the return tracks; sources mention roughly 150-250 Hz for reverb.

## B. Clarity and balance (11-20)

11. **Frequency masking.** Two sounds occupy the same range and hide each other. Decide which matters more and cut the other where they clash.
12. **Too many layers.** Mute elements one at a time. Clarity usually comes from taking things away.
13. **Fixing arrangement problems with EQ.** No plugin rescues a cluttered arrangement. Simplify the parts first.
14. **Weak source sounds.** A thin sample caps how good the mix can get. Swap the sound before processing it.
15. **Everything at the same volume.** Pick the lead element and build a hierarchy around it.
16. **Boxy midrange.** Boxiness lives in the low-mids. Sweep a boost to find it, then cut a little.
17. **Boosting instead of cutting.** Sweep and cut problem spots before adding anything. Boosts bring harshness and ear fatigue.
18. **Ringing resonances.** Sharp peaks cloud a mix. Find them by sweeping a boost on Channel EQ's mid band, then cut a little. Its cuts are broad, so a Q-controllable EQ does this better.
19. **Unnatural carving.** Rolling off natural highs on kick and bass, or lows on vocals, makes them thin or dull. Cut only what a track doesn't need.
20. **Everyone piles onto 2-4 kHz.** Everything wants presence there. Give that lane to the lead and ease the others out of it.

## C. Vocals (21-30)

21. **Vocal buried.** Before boosting the vocal, cut competing instruments around 1-4 kHz. Then add a small boost near 2-3 kHz if needed.
22. **Harsh vocal (about 2-5 kHz).** A couple of dB of broad cut helps. Cut too much and it gets buried, so make small moves.
23. **Sibilance (about 5-8 kHz).** Live Intro has no de-esser. Worth testing: the Compressor's sidechain filter (SC Filter) aimed at the S range, or volume automation on the loudest S sounds.
24. **Thin or distant vocal.** Check recording level and presence range, and reduce reverb before adding anything.
25. **Muddy vocal.** High-pass around 80-100 Hz, then a 2-3 dB cut around 200-350 Hz.
26. **Plosives and pops.** Best fixed at recording (pop filter, mic slightly off-axis). A high-pass helps afterward.
27. **Uneven vocal level.** Compress for roughly 4-8 dB of reduction on peaks, then automate volume on individual words.
28. **Nasal or honky vocal.** Look between 500 Hz and 1 kHz, gently. Over-cutting there sounds hollow.
29. **Vocal doubles sound blurry.** Doubles should thicken, not blur. Check timing and avoid stereo wideners on top of them.
30. **No air.** A gentle high shelf of 1-3 dB adds openness. Overdo it and the vocal turns harsh.

## D. Drums and punch (31-40)

31. **Drums lack punch.** Punch lives in the first milliseconds. Protect the transients and reduce low-end overlap.
32. **Drum bus compression kills punch.** Try a slower attack (around 20-30 ms), a ratio of 2:1 to 4:1, and 2-4 dB of reduction.
33. **Hi-hats and cymbals too harsh.** High-pass around 300-500 Hz and cut harshness near 2-4 kHz before adding shimmer.
34. **Snare thin or ringing.** Find the ring with a narrow sweep and cut it. Body sits around 200 Hz and crack near 5 kHz.
35. **Drums sound like separate samples.** Gentle bus compression makes them feel like one kit.
36. **Layered kicks or snares cancel.** Flip polarity on one layer (Utility's Ø button) or nudge its timing.
37. **Uneven hits and ghost notes.** Edit velocities and use light compression.
38. **Melody masks the drums.** Turn the melody down and clean its low end before adding more plugins to the drums.
39. **Master limiter flattens transients.** Default limiters left on the master crush attacks. Remove them while mixing.
40. **Layers hit at slightly different times.** Zoom in and align the attacks. Sloppy timing smears the hit.

## E. Compression and dynamics (41-50)

41. **Compressing everything by default.** Compress only when you hear a problem it solves. Over-compression squashes life out of a mix.
42. **Using compression to repair a bad take or arrangement.** Fix performance, levels and EQ first.
43. **Not level-matching.** A louder version always sounds better. Use makeup gain to match, then bypass and compare.
44. **Attack and release set blindly.** A slow attack lets the transient through, a fast one flattens it. Release should recover before the next note.
45. **Pumping.** Release too fast, especially on buses. Slow it down or use Auto.
46. **Too much reduction in one compressor.** More than about 8 dB usually sounds bad. Two gentle stages beat one heavy one.
47. **Compressing mud.** Fix obvious EQ problems first so the compressor reacts to the good part of the sound.
48. **Sidechain everywhere.** Use it on a few elements that take the most space. Give ducked reverbs a long enough release.
49. **OTT on everything.** Its Depth at 100% is extreme. Lower Depth or the dry/wet, and use it on one or two sounds on purpose.
50. **Copying settings between tracks.** Different sources behave differently. Start from what the sound is doing.

## F. Space, reverb and delay (51-60)

51. **Too much reverb.** Aim to feel it more than hear it. If muting it makes the mix sound deflated, it's about right.
52. **Reverb as an insert at 50% wet.** Use a send (100% wet on the return) so the dry signal stays clean. Your template already has A Reverb and B Delay returns.
53. **No high-pass on reverb returns.** The most common home-studio mud source. Cut the lows from the return.
54. **Zero pre-delay on lead sounds.** Reverb starting instantly makes vocals washy. A little pre-delay keeps them clear.
55. **Decay too long for the tempo.** Long tails in a busy arrangement blur the groove. Shorten the decay.
56. **Too many different reverbs.** Eight rooms sound like a collage. Two or three shared sends hold a mix together.
57. **Delays muddy or invisible on phones.** High-pass and filter the delay return.
58. **No front-to-back depth.** Mixes feel flat when everything is equally close. Use different send amounts and pre-delay to place sounds nearer or farther.
59. **Hidden reverb in presets.** Amp sims and channel strips sometimes have reverb on by default. Check every device.
60. **Constant wash.** Reverb on everything all the time tires the ear. Use shorter tails in quiet sections and automate the send.

## G. Stereo, width and phase (61-70)

61. **Everything panned center.** Sounds fight for the same spot. Panning gives them separate space.
62. **Everything wide.** A wide-everything mix loses its center and its impact. Keep key sounds in the middle.
63. **Fake widening.** Wideners and phase tricks on mono sources collapse in mono. Build width from real differences: doubles, different sounds left and right, stereo reverbs on sends.
64. **Mix falls apart in mono.** Many phones and speakers are near-mono. Check mono often.
65. **Phase cancellation from layering.** Same-ish sounds layered together can thin each other out. Check with polarity flips.
66. **Stereo delays and chorus lose level in mono.** Mono-check anything that widens.
67. **Width in the lows.** Keep the bottom centered. Utility's Bass Mono handles this.
68. **Extreme panning.** A hard-panned sound can vanish on one earbud or collapse in mono. Pan with purpose.
69. **Never checking mono at all.** Make Utility's Mono button part of your routine.
70. **Too many pan positions.** The ear can distinguish only a few. Use a few clear positions instead of many similar ones.

## H. Levels, headroom and loudness (71-80)

71. **Recording too hot.** Digital clipping is harsh and can't be fixed later. Record with room to spare.
72. **Poor gain staging into plugins.** Many plugins behave best around -18 dBFS average. Trim the input with Utility's gain before a plugin that reacts to level.
73. **Faders at extremes.** Faders far above or below zero point to level problems upstream. Adjust source gain, then keep faders near the middle of their range.
74. **No headroom on the master.** Peaks around -6 dBFS before mastering leave room for everything after.
75. **Chasing loudness while mixing.** Loudness is a mastering job. Build a balanced mix first.
76. **Over-limiting the master.** Streaming services normalize volume, so extra squash only costs dynamics.
77. **Not knowing streaming targets.** A common target is around -14 LUFS with true peak near -1 dBTP. Sources differ, so treat it as a starting point.
78. **Master-bus processing left on.** Leftover limiters and effects change how everything sounds. Check what's on the master.
79. **Sub buildup limits loudness.** Excess low energy makes the limiter work hard. Control the sub and the mix gets louder cleanly.
80. **Handing a hot mix to mastering.** Give a mix with peaks near -6 dBFS and no limiter on the bus.

## I. Monitoring and workflow (81-90)

81. **Mixing in solo.** A track that sounds great alone can clash in the mix. Decide with everything playing.
82. **Monitoring too loud.** Loud sounds better and hides problems. Mix mostly at moderate levels (sources say roughly 75-85 dB SPL).
83. **Ear fatigue.** Take breaks (a short one every hour, some sources say every 45 minutes) and come back fresh.
84. **One listening system.** Check headphones, phone, laptop and car.
85. **No reference tracks.** Pick two or three finished tracks in your genre and switch between them and your mix.
86. **References at different volume.** Match volume before comparing, or the louder one wins.
87. **Headphones exaggerate lows and highs.** Cross-check on other systems and use references.
88. **The room lies.** Bad acoustics hide low-end problems. Check on other systems.
89. **Plugins before balance.** Rebuild with faders and panning first, then process.
90. **Endless tweaking.** Take a break, sleep on it, and listen the next day before finalizing.

## J. Digital-specific and finishing (91-100)

91. **Digital clipping anywhere in the chain.** It can happen on any track or device, not only on the master. Watch levels at each stage.
92. **Aliasing from saturation and distortion.** Harsh, metallic artifacts on cymbals and highs. Oversampling helps where a device offers it.
93. **Oversampling on everything.** It multiplies CPU load. Use it only where you hear a problem.
94. **CPU overload, crackles and dropouts.** Freeze heavy tracks or increase the buffer size.
95. **Clicks while recording.** A too-small buffer can cause them. Raise the buffer size while tracking.
96. **Phase issues from oversampling and latency.** Aux sends can sound phasey when processed and dry signals recombine. Try inserts with a dry/wet control.
97. **Inter-sample peaks after export.** Peaks between samples can distort when encoded. Leave a small ceiling (true peak near -1 dBTP).
98. **A static mix.** Levels, panning and effects that never change feel robotic. Automate volume, filters, sends and pans.
99. **Sample-rate mismatch.** Files at a different rate than the session can cause metallic artifacts. Keep source files and session consistent.
100. **Not checking the final bounce.** Listen to the export on a phone and in the car, at low volume, in mono, before calling it done.

---

## Sources consulted

LANDR Blog, Sound On Sound, Mastering The Mix, ProducerHub, Audiospectra, Sonnox, SoundGym, Ableton Forum and Gearspace threads, Icon Collective, Soundation, Pro Audio Files, and various producer education sites. Where they disagreed on numbers, this document keeps ranges and hedges.
