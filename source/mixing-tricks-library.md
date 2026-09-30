# Mixing Tricks Library

Detailed tricks for the 100 pain points, built for Ableton Live Intro and the FX rack (**Channel EQ, Compressor, OTT, Utility**). Companion to the 100 Mixing Pain Points list. This page grows one group at a time.

**Numbers are starting points.** They come from tutorials and articles that sometimes disagree, so use them as a first move and trust your ears.

**Two things to know about your rack**
- Turning the rack on switches on all four devices. Inside it, click the small power button on any device (OTT, for example) to keep just the ones you want.
- Channel EQ's high-pass switch sits at a fixed frequency (about 80 Hz). That is right for pads, guitars and vocals, and wrong for kick, bass or 808, whose main energy sits below it.

---

## A. Low end (pain points 1-10)

### The 5-minute low-end routine
1. Play the loudest section and press Utility's **Mono** button on the master or the group. Does the low end stay strong?
2. Switch on Channel EQ's **high-pass** on every track that is not kick, bass or 808.
3. Decide who owns the sub: kick or bass. Give the other one less down there.
4. Sidechain the bass to the kick if they still blur.
5. Play it on a phone speaker. Can you still hear the bass line?

### 1. Kick and bass fight for the same space
**Why:** both live in the same low frequencies, and their waveforms stack.
**Try this:**
- **Pick an owner for the sub.** Guides suggest giving the kick weight around 50-80 Hz and letting the bass carry its body above that, or the reverse. One sound owns the deepest notes.
- **Use the Low knob on Channel EQ.** A small cut on the one that doesn't own the sub, a small boost on the one that does.
- **Sidechain the bass to the kick** (see trick 4 below for the setup).
- **Offset the hits if the groove allows.** One source notes that avoiding overlaps between kick and bass can help, but it is not a hard rule.
**Watch for:** boosting both. That makes the low end louder and muddier.

### 2. Low-mid mud (roughly 200-500 Hz)
**Why:** vocals, guitars, keys, pads, bass and reverb all add energy here, and it piles up.
**Try this:**
- **Find who is adding it.** Mute tracks one at a time and listen for the mud to thin out.
- **Cut small and on several tracks.** Use Channel EQ's mid band, sweep to 200-500 Hz, and take away 1-3 dB on the culprits.
- **Don't cut the same range on every track.** Identify the sources first.
**Watch for:** cutting so much that things sound thin. Compare with bypass.

### 3. Rumble nobody can hear
**Why:** many sounds carry low content that eats headroom without adding anything you hear.
**Try this:**
- **Channel EQ high-pass** (about 80 Hz) on guitars, vocals, pads, hats and percussion.
- **Go higher on pads and synths.** Guides suggest roughly 100-200 Hz for them. If Auto Filter is in your browser, its high-pass can go higher than 80 Hz.
**Watch for:** using the 80 Hz switch on kick, bass or 808.

### 4. Kick is loud but has no punch
**Why:** the attack (the click) is hidden, or the compressor closes on it, or the bass masks it.
**Try this:**
- **Compressor attack 10-30 ms.** A slower attack lets the click through. Sources suggest 3-6 dB of gain reduction for a kick.
- **Clear the boxiness.** A small cut around 250-400 Hz with Channel EQ's mid band. It has no Q control, so the cut is fairly broad.
- **Add click.** A small boost near 3-4 kHz on the mid band.
- **Skip OTT on the kick** unless you want it squashed.
**Watch for:** judging without level-matching. Match volume with makeup gain before you compare.

### 4b. Sidechain the bass to the kick
1. Put the kick on its own track (a sidechain from a drum track ducks on every hit in it).
2. On the bass track, turn the rack on and keep only Compressor active.
3. Open the Compressor's sidechain section (the small triangle at its left edge), turn Sidechain on, and choose the kick's track under **Audio From**.
4. Raise the ratio and lower the threshold until the bass dips a few dB on each kick. Use a fast attack and a release that lets the bass return before the next kick.
5. Keep it subtle. Extreme settings sound like pumping, which you may want in dance music but not elsewhere.

### 5. Wide bass, sloppy low end
**Why:** stereo information in the lows makes them unstable and can cancel in mono.
**Try this:**
- **Utility → Bass Mono.** Below its set frequency (your Utility shows 120 Hz) the signal becomes mono. Sources suggest keeping lows mono somewhere between 100 and 150 Hz.
- **Or lower Width.** Utility's Width at 0% is mono.
**Watch for:** switching Bass Mono on with no comparison. Toggle it and listen.

### 6. Kick and bass cancel each other
**Why:** their waveforms are out of step, so some low frequencies subtract.
**Try this:**
- **Mono check.** If the low end shrinks or vanishes in mono, suspect phase.
- **Flip polarity.** On the bass, click both **Ø L and Ø R** in Utility together (flipping only one breaks the stereo image), and compare. Keep whichever is fuller.
- **Nudge timing** of one layer if flipping doesn't help.
**Watch for:** fixing this with EQ boosts. If it's phase, more level won't help.

### 7. Long 808 or sub tails overlap
**Why:** sustained low notes run into each other and into the kick.
**Try this:**
- **Shorten the notes** in the MIDI clip so each ends before the next hit.
- **Shorten the instrument's release or decay** if it has one.
- **Sidechain to the kick** as in 4b, so the tail steps aside.
**Watch for:** clipping the tail so short it sounds like a click.

### 8. Too much sub energy
**Why:** excessive low energy triggers the limiter early, so the whole mix stays quiet.
**Try this:**
- **Trim with Channel EQ's Low knob** on anything that doesn't need it.
- **Watch the master meter.** If it jumps on every kick, reduce the sub.
**Watch for:** removing so much that the track loses weight on big speakers. Compare on more than one system.

### 9. Bass vanishes on phone and laptop speakers
**Why:** small speakers can't reproduce true sub, so a bass that is all sub disappears.
**Try this:**
- **Add upper harmonics.** Guides suggest bass harmonics above roughly 90 Hz for presence. If Saturator is in your browser, use it lightly on the bass; a quiet copy of the bass an octave up, high-passed, also works.
- **Test on a phone speaker** (not Bluetooth).
**Watch for:** adding so much that the bass gets harsh.

### 10. Reverb and delay carry low end
**Why:** low frequencies in tails add mud and blur the kick and bass.
**Try this:**
- **Reverb's input filter.** Live's Reverb has one; cut the lows below roughly 150-250 Hz, as guides suggest.
- **Or Channel EQ on the return track** with high-pass on, and the Low knob pulled down.
- **Do the same on delay returns.**
**Watch for:** cutting too high and making the reverb thin.

---

## B. Clarity and balance (pain points 11-20)

**A note on Channel EQ.** Its Mid band has only frequency and gain controls (no Q), so its cuts and boosts are fairly broad. That is fine for shaping and gentle carving. Surgical, narrow cuts need an EQ with a Q control, such as EQ Eight in Live Standard.

### The clarity routine
1. **Static mix first.** Strip the plugins (or bypass the rack) and balance with faders and panning only. Get the lead, the kick and bass, and the snare sitting right.
2. **Mute test.** Mute one element at a time. If the mix opens up, that element was crowding it.
3. **Fix sounds before processing.** Swap a weak sound instead of EQ-ing it.
4. **Then EQ, gently.** Cut before you boost.

### 11. Frequency masking
**Why:** two sounds occupy the same frequency range, so one hides the other.
**Try this:**
- **Decide who matters more** in that moment, then cut the other where they clash.
- **Use Channel EQ's mid band** on the less important sound, a few dB down at the shared range.
- **Pan them apart** if the arrangement allows. Different positions help separation.
**Watch for:** cutting in solo. Make the decision with everything playing.

### 12. Too many layers
**Why:** each extra layer takes space, and clutter costs energy and clarity.
**Try this:**
- **Mute elements one at a time** and listen for the mix opening up.
- **Remove what doesn't earn its place.** One guide puts it simply: clarity comes more from subtraction than addition.
- **Split sections.** If a part must play in a breakdown alone, duplicate the track (one for the breakdown, one for the drop) and EQ each for its job.
**Watch for:** adding a plugin to hide a weak sound. That usually adds another layer of clutter.

### 13. Fixing arrangement problems with EQ
**Why:** if parts fight in time and pitch, EQ can only shave the surface.
**Try this:**
- **Change the arrangement first.** Move a part to a different octave, thin its notes, or let it rest while another plays.
- **Use automation** to bring parts in and out instead of stacking them all the time.
**Watch for:** spending an hour on EQ moves when muting one part would have fixed it.

### 14. Weak source sounds
**Why:** a thin or dull sample sets a ceiling that mixing can't raise.
**Try this:**
- **Audition replacements in context,** with the full track playing.
- **Layer with a purpose:** one sound for weight, one for click, checking phase (Utility's Mono button and Ø buttons).
**Watch for:** judging a sound in solo. It has to work with everything else.

### 15. Everything at the same volume
**Why:** without a hierarchy, the listener doesn't know where to focus.
**Try this:**
- **Pick the star.** For most songs it is the vocal or the lead.
- **Set levels in order of importance:** the lead first, then kick and bass locked together, then the snare, then the rest around them.
- **Use faders, not plugins.** Only touch EQ once the balance is close.
**Watch for:** raising everything to feel louder. Turn things down instead.

### 16. Boxy midrange
**Why:** too much energy in the low-mids makes sounds feel closed in and cardboard-like.
**Try this:**
- **Sweep to find it.** On Channel EQ, raise the Mid gain and sweep the frequency through roughly 200-500 Hz until the box sound jumps out.
- **Then turn it into a small cut,** a few dB at most.
- **Bypass to compare** and match volume with the Output knob.
**Watch for:** hollow-sounding results. That means too much cut.

### 17. Boosting instead of cutting
**Why:** boosts add harshness and fatigue, and they raise the level, which fools you into thinking it sounds better.
**Try this:**
- **Cut first.** Find the problem spot and lower it before adding anything.
- **Boost only to shape,** and keep boosts small.
- **Match levels with the Output knob** so you compare tone, not loudness.
**Watch for:** stacking boosts on several tracks. The mix gets harsher without any single track sounding wrong.

### 18. Ringing resonances
**Why:** a sharp peak at one frequency clouds a sound, and it often hides in one instrument.
**Try this:**
- **Sweep to find it** with Channel EQ's mid boost, listening for a note-like ring that jumps out.
- **Cut it,** accepting that Channel EQ's cut is broad. Keep it small.
- **If you need surgical precision,** an EQ with a Q control (EQ Eight, in Live Standard) does this better.
**Watch for:** carving away the sound's character along with the ring.

### 19. Unnatural carving
**Why:** removing too much from a track can leave it thin or dull, even if the mix clears up.
**Try this:**
- **Cut only what a track doesn't need,** not everything outside its main range.
- **Keep some body** on vocals and some high end on bass and kick.
- **Check in context.** Compare with the rack on and off with everything playing.
**Watch for:** the "carve every instrument into its own slice" habit. It can make each part sound small.

### 20. Everyone piles onto 2-4 kHz
**Why:** presence and edge live here, so every part wants it.
**Try this:**
- **Give the lane to the lead,** usually the vocal.
- **On competing tracks,** use Channel EQ's Mid at around 3 kHz with a small cut, 1-2 dB.
- **If a part gets buried,** first try cutting the other parts here before raising the lead.
**Watch for:** cutting so much that guitars or synths lose their bite.

---

## C. Vocals (pain points 21-30)

### A starting vocal chain
1. **Channel EQ:** high-pass on (about 80 Hz), a small cut around 250-300 Hz if it sounds muddy, a small boost near 2-3 kHz if it needs presence.
2. **Compressor (levelling):** ratio 3:1 to 4:1, attack 10-30 ms, release Auto or 100-200 ms, and threshold set for roughly 4-8 dB of reduction on the loudest parts. Ease off if it sounds squashed.
3. **A second Compressor as a de-esser** (see 23), placed after the first one, since compression tends to bring sibilance up.
4. **Reverb send** with a little pre-delay so the vocal stays clear.
5. **Volume automation** for the last bit of evenness.

### 21. Vocal buried
**Why:** instruments compete for the same range the vocal needs to be understood.
**Try this:**
- **Cut the instruments first.** Put Channel EQ on the competing tracks and take 1-2 dB out around 1-4 kHz before raising the vocal.
- **Then add presence** to the vocal with Channel EQ's Mid around 2-3 kHz, 1-3 dB.
- **Check the reverb.** Too much wet pushes the vocal back.
**Watch for:** boosting the vocal until it is louder than everything, then the mix has no balance.

### 22. Harsh vocal (about 2-5 kHz)
**Why:** the singer, the mic and the room can all add edge in this range, and processing can make it worse.
**Try this:**
- **Take out a few dB with Channel EQ's Mid** around 3-4 kHz, with a broad cut.
- **Check your own chain.** Bypass processors from the last one back to the first. If harshness disappears when a device is bypassed, that device caused it.
- **Remember OTT.** Its upward compression can raise edge and noise. Keep it off the vocal or use a very low Depth and dry/wet.
**Watch for:** cutting too much. The same range helps a vocal cut through, and too much cut buries it.

### 23. Sibilance (about 5-8 kHz)
**Why:** S and T sounds get sharp, especially after EQ boosts and compression.
**Try this (Live Intro has no de-esser):**
1. Add a **second Compressor** after your levelling compressor.
2. Open its sidechain section and turn **SC Filter** on. Set the filter so the compressor listens to the high frequencies (its Type dropdown includes a high-pass shape; start around 5-6 kHz).
3. Use a fast attack, a fast release, and a higher ratio.
4. Bring the threshold down until it dips only on the S sounds. The headphone button should let you hear what the compressor is reacting to.
5. **Fallback:** ride the volume down on the worst S sounds with automation.
**Watch for:** a lisp. That means too much reduction.
**Prevent it at the source:** a mic angled slightly off-axis, and a little more distance from the mic, both reduce sibilance in the first place.

### 24. Thin or distant vocal
**Why:** it can come from level, missing presence, too much reverb or too little body.
**Try this:**
- **Reduce the reverb** first and add a little pre-delay to the send.
- **Check the low end.** A small boost with Channel EQ's Low knob adds body.
- **Add presence** around 2-3 kHz, gently.
- **Compress lightly** so quiet phrases stay in front.
**Watch for:** boosting everything at once. Change one thing at a time and compare.

### 25. Muddy vocal
**Why:** too much low-mid energy, often from a close mic (the proximity effect) or a small room.
**Try this:**
- **Channel EQ high-pass** on (about 80 Hz).
- **Cut 2-3 dB** with the Mid around 200-350 Hz.
**Watch for:** over-cutting until the voice sounds hollow.

### 26. Plosives and pops
**Why:** bursts of air on P and B sounds hit the mic.
**Try this:**
- **Fix it at the source.** A pop filter and the mic slightly off-axis.
- **In the mix,** use Channel EQ's high-pass and lower the volume on the pop with automation.
**Watch for:** heavy EQ to hide a pop. It thins the whole vocal.

### 27. Uneven vocal level
**Why:** phrases and words vary in loudness, and a compressor can't fix every one.
**Try this:**
- **Two light stages** often sound more natural than one heavy stage (one guide suggests roughly 4:1 followed by 2:1).
- **Ride the volume** with automation on quiet words and loud endings.
**Watch for:** more than about 8 dB of reduction in a single compressor, which usually sounds squashed.

### 28. Nasal or honky vocal
**Why:** energy between about 500 Hz and 1 kHz.
**Try this:**
- **Sweep Channel EQ's Mid** through that range with a boost to find the honk, then turn it into a small cut.
- **Check recording position.** A different mic angle sometimes fixes it better than EQ.
**Watch for:** hollowness from over-cutting.

### 29. Vocal doubles sound blurry
**Why:** timing or pitch differences smear the edges, or copies of the same take sit on top of each other.
**Try this:**
- **Use real doubles,** separate takes, not copies. Real differences widen without cancelling.
- **Pan the doubles** moderately left and right, and keep the lead in the center.
- **Set the doubles lower** than the lead so they thicken it without competing.
- **Check mono** with Utility's Mono button.
**Watch for:** a stereo widener on top of doubles.

### 30. No air
**Why:** the top end is dull or missing.
**Try this:**
- **Channel EQ's High knob** (a high shelf) up 1-3 dB.
- **Check sibilance afterwards.** Boosting the top often brings it back.
**Watch for:** harshness. If it gets edgy, back off.

---

## D. Drums and punch (pain points 31-40)

### The punch routine
1. **Balance and masking first.** Is the melody too loud? Are kick and bass fighting? (See A and B.)
2. **Test the compressor attack.** Shorten the attack until the punch disappears, then back off until it returns.
3. **Glue the kit on a group.** Select the drum tracks and press Cmd+G, then put a Compressor on the group.
4. **Add parallel compression** if the drums need weight without flattening. Compressor's Dry/Wet knob does this without a return track.
5. **Check the Main track** for a limiter that could be flattening everything.

### 31. Drums lack punch
**Why:** punch lives in the first few milliseconds of each hit. Masking, over-compression, or a flattened attack all hide it.
**Try this:**
- **Clear the way.** Lower a melody that is too loud, and sort out kick-and-bass overlap.
- **Slow the attack** on the drum compressor so the click passes before compression starts.
- **Try parallel compression.** On the Compressor, set a heavier ratio and threshold, then use the Dry/Wet knob to blend it in, starting around half.
- **Create contrast.** Let drums drop out briefly before a big section so the return hits harder.
**Watch for:** raising the level to get impact. That usually just makes the mix louder.

### 32. Drum bus compression kills punch
**Why:** a fast attack grabs the transient, and heavy reduction flattens it.
**Try this:**
- **Starting point:** ratio 2:1 to 4:1, attack about 20-30 ms, release 100-200 ms, and 2-4 dB of gain reduction.
- **Bypass and compare** with the volume matched using makeup gain.
- **Adjust the attack by ear.** Too fast kills the punch, too slow misses the peaks.
**Watch for:** compressing on every individual drum track and again on the group. It stacks quickly.

### 33. Hi-hats and cymbals too harsh
**Why:** they carry a lot of energy in the 2-4 kHz range and are easy to overdo.
**Try this:**
- **Channel EQ high-pass** on (about 80 Hz), and pull the Low knob down to remove more low end. Guides suggest going as high as 300-500 Hz on hats.
- **Cut harshness first** with the Mid band around 2-4 kHz.
- **Add shimmer last,** with the High knob up 1-3 dB.
- **Skip heavy compression.** Hats are already fairly consistent, and one guide suggests 1-2 dB at most.
**Watch for:** hats that mask the vocal in the same range.

### 34. Snare thin, boxy or ringing
**Why:** the body, the box and the crack sit in different ranges and can be out of balance.
**Try this:**
- **Body:** a small boost around 200 Hz with the Mid band.
- **Box:** a small cut around 400-500 Hz.
- **Crack:** a small boost near 5 kHz.
- **Ring:** find it by sweeping a boost, then cut it a little.
- **Compression:** guides suggest roughly a 15-25 ms attack and 4-6 dB of reduction as a starting point.
**Watch for:** Channel EQ's Mid band is broad, so move one band at a time and compare.

### 35. Drums sound like separate samples
**Why:** each hit sits on its own, with nothing tying them together.
**Try this:**
- **Bus compression** as in 32.
- **One shared short reverb** on a send for a common space.
- **A small cut around 300-500 Hz on the group** (one guide suggests 1-2 dB) to tighten the kit.
**Watch for:** over-gluing until the kit sounds dull.

### 36. Layered kicks or snares cancel
**Why:** two layers start at slightly different points, so some frequencies subtract.
**Try this:**
- **Flip polarity.** Click both **Ø L and Ø R** in Utility on one layer, then compare.
- **Nudge timing** of one layer so the attacks line up.
- **Let one layer own the low end.** High-pass the other with Channel EQ.
- **Check mono** with Utility's Mono button.
**Watch for:** a flip that makes one layer quieter or thinner. Compare both versions.

### 37. Uneven hits and ghost notes
**Why:** velocity and level differences make some hits jump out or vanish.
**Try this:**
- **Edit velocities** in the MIDI clip.
- **Use clip gain** on audio clips for individual hits.
- **Compress lightly** to even things out.
**Watch for:** removing all variation. Some difference is what makes a groove feel alive.

### 38. Melody masks the drums
**Why:** loud melodies and their low-mids take up the space drums need.
**Try this:**
- **Lower the melody first,** before adding anything to the drums.
- **Clean its low end** with Channel EQ's high-pass and the Low knob, since loops often carry energy around 100-300 Hz.
- **Listen again.** Drums often regain their impact with no extra processing.
**Watch for:** stacking EQs and compressors on the drums to fix a balance problem.

### 39. Master limiter flattens transients
**Why:** a limiter that stays on the master crushes attacks as the mix gets louder.
**Try this:**
- **Check the Main track's device chain** for a limiter and bypass it while mixing.
- **Leave headroom,** with peaks around -6 dBFS, and push loudness only later.
- **Compare with the limiter bypassed** to hear what it costs.
**Watch for:** judging punch through a limiter you forgot was on.

### 40. Layers hit at slightly different times
**Why:** attacks that don't line up smear the hit.
**Try this:**
- **Zoom in on the waveforms** and align the starts.
- **Use Live's Track Delay** (in the mixer section) to shift a whole track by a few milliseconds.
- **Move the clip** slightly if it is one clip.
**Watch for:** perfect alignment on recorded drums. Small timing differences between mics can give depth, so this matters most for layered samples.

---

## E. Compression and dynamics (pain points 41-50)

### Your Compressor in two analogies
- **Threshold is a ceiling.** Anything that rises above it gets pushed down. A lower ceiling catches more of the sound.
- **The whole device is a hand on the volume knob.** It turns loud parts down for you. Attack is how fast the hand reacts, release is how fast it lets go, and ratio is how firmly it pushes.

Useful controls on yours: **Thresh** and **Ratio**, **Attack**, **Release** (with an **Auto** button), the **GR** meter (gain reduction), **Makeup** (automatic level compensation) and **Out** (manual output level), **Peak / RMS** (how it measures the signal), and **Dry/Wet**.

### Starting points by source
These come from several guides. They differ a little, so use them as a first move.

| Source | Attack | Release | Gain reduction to aim for |
|---|---|---|---|
| Lead vocal | 10-30 ms | Auto, or 100-200 ms | roughly 4-8 dB |
| Kick | 10-30 ms | 50-150 ms | roughly 3-6 dB |
| Snare | 10-25 ms | 50-100 ms | roughly 4-6 dB |
| Drum bus | 20-30 ms | 100-200 ms | roughly 2-4 dB |
| Hi-hats | fast | fast | 1-2 dB, if any |

### 41. Compressing everything by default
**Why:** compression feels professional, so it gets added everywhere, and the mix loses life.
**Try this:**
- **Ask what problem it solves** before you add it: uneven level, peaks that jump out, a sound that needs to sit forward.
- **Bypass and compare** (with volume matched). If you can't hear a benefit, leave it off.
- **Use small amounts.** One guide says 2-4 dB on peaks is control you don't hear working, and 6-10 dB is an audible effect that changes the character.
**Watch for:** habit. Your rack's bypass-by-default design helps here, because you turn compression on only when needed.

### 42. Using compression to repair a bad take or arrangement
**Why:** compression can't fix a performance, a level, or a clash in the arrangement.
**Try this:**
- **Fix upstream first:** the take, the gain, the EQ, the arrangement.
- **Treat compression as a finishing tool.**
- **If you need lots of reduction,** ask whether the real problem is earlier in the chain.
**Watch for:** stacking compressors to smooth a problem that a re-take or edit would remove.

### 43. Not level-matching
**Why:** louder sounds better to human ears, so an unmatched compressor always seems like an improvement.
**Try this:**
- **Match output to input** with the **Out** knob, or the **Makeup** button for automatic compensation. Manual matching is more precise, and automatic is fine while learning.
- **Bypass and compare** at equal volume.
- **Repeat this check** every time you change a compressor setting.
**Watch for:** accepting a setting because it is louder.

### 44. Attack and release set blindly
**Why:** the two controls decide whether a compressor keeps the life in a sound or takes it out.
**Try this:**
- **Attack:** a slower attack (roughly 20-50 ms) lets the click through. A very fast one (1-5 ms) controls peaks but sounds less natural.
- **Set attack by listening to the hit.** Shorten it until the punch disappears, then back off until it returns.
- **Set release between the hits.** Lengthen it until the sound stops "breathing." Ideally the gain reduction returns to zero just before the next note.
**Watch for:** setting both once and never revisiting them when the part changes.

### 45. Pumping
**Why:** the release is too fast, so the level jumps back up between hits.
**Try this:**
- **Lengthen the release** or switch on **Auto**, which follows the material.
- **Lower the reduction** with a higher threshold or lower ratio.
- **Use a slower release on buses.** One guide describes 10-100 ms releases as audible pumping and 200-1000 ms as invisible levelling.
**Watch for:** pumping you like. In dance music it can be a deliberate effect. Make it a choice.

### 46. Too much reduction in one compressor
**Why:** heavy reduction from one device shows up as squashed sound and artifacts.
**Try this:**
- **Split the job.** Two gentle stages usually sound more natural than one hard one.
- **Keep one stage under about 8 dB.**
- **Try parallel** with the Dry/Wet knob when you want density without losing the original.
**Watch for:** the meter sitting at 5-6 dB all the time. That usually means the threshold is too low or the ratio too high.

### 47. Compressing mud
**Why:** the compressor reacts to the loudest energy, and low-mids and lows often dominate.
**Try this:**
- **EQ first.** Remove obvious mud and rumble so the compressor works on the good part of the sound.
- **Check the SC Filter** in the Compressor's sidechain section. With it on, the compressor reacts less to low frequencies (the default around 80 Hz behaves like a high-pass).
- **Compare bypassed** with matched levels.
**Watch for:** pumping on bass notes. That points to the lows triggering the compressor.

### 48. Sidechain everywhere
**Why:** ducking every element makes the whole mix pump and lose weight.
**Try this:**
- **Pick a few elements** that take the most space, such as bass, pads or a big synth.
- **Keep it subtle.** A few dB on each kick is usually enough.
- **Use a longer release** (200 ms or more) if you are ducking a reverb, so the tail doesn't pump.
**Watch for:** a ducked bass that vanishes. Set the reduction so it stays audible.

### 49. OTT on everything
**Why:** OTT squashes the loud and lifts the quiet parts in three frequency bands at once. It sounds huge, and it flattens contrast.
**Try this:**
- **Lower Depth and Time** from 100%, and use it on one or two sounds on purpose.
- **Match the level** with its Out Gain, since it usually makes things louder.
- **Blend it in.** Keep the mix of OTT low on drums or synths for energy without the full effect.
- **Keep it away from vocals** unless you want the effect, because it can lift breaths and harshness.
**Watch for:** a mix where everything is loud and nothing stands out.

### 50. Copying settings between tracks
**Why:** different sounds behave differently. A fast, spiky kick needs something different than a sustained pad.
**Try this:**
- **Start from the source.** Quick, sharp sounds need a slower attack to keep the click. Sustained sounds need a slower release to avoid pumping.
- **Use the table above** as a starting point, then adjust by ear.
- **Save variations of your rack** for different jobs (drums, vocals, bass) with the Compressor set differently.
**Watch for:** copying a setting because it worked once.

---

## F. Space, reverb and delay (pain points 51-60)

Your template already has two return tracks, **A Reverb** and **B Delay**. Each track's **A** and **B** send knobs feed them, and the **Post** buttons on the returns mean the sends follow each track's fader, so muting a source also mutes its reverb.

### The space routine
1. **Use the returns** for reverb and delay, with the device set to 100% wet.
2. **Cut the lows** on both returns.
3. **Set pre-delay and decay** for the sound you're placing.
4. **Set the send levels** by ear, then mute the returns to check what you added.
5. **Mono and phone check** to catch wash and stereo problems.

### 51. Too much reverb
**Why:** it's the easiest way to make a mix sound amateur, and it builds up without you noticing.
**Try this:**
- **Aim to feel it more than hear it.** Mute the reverb return. If the mix sounds a bit deflated, the level is about right. If nothing changes, you can add a little more. If it sounds better dry, you have too much.
- **Once you hear it clearly,** back it off a touch.
- **Set amounts per sound,** not one level for everything.
**Watch for:** judging reverb with your ears fresh. Recheck after a break.

### 52. Reverb as an insert at 50% wet
**Why:** blending wet and dry inside one device can cause phase problems with the dry signal and removes your control over the reverb alone.
**Try this:**
- **Put reverb on a return** and set its Dry/Wet to 100%.
- **Send to it** with each track's A send.
- **Keep the Post button on.** A pre-fader send keeps the reverb playing after you mute the source.
**Watch for:** using the reverb as an insert just because it's quicker.

### 53. No high-pass on reverb returns
**Why:** low frequencies in a reverb tail add mud and hide the kick and bass. Guides call it the most common home-studio reverb mistake.
**Try this:**
- **Reverb's input filter.** Cut the lows below roughly 150-250 Hz.
- **Or Channel EQ on the return,** with the high-pass on and the Low knob pulled down.
- **Solo the return** and listen for boom.
**Watch for:** cutting so high that the reverb sounds thin. Check in context.

### 54. Zero pre-delay on lead sounds
**Why:** when the reverb starts the instant the dry sound does, the tail smears the front of the word or hit.
**Try this:**
- **Add pre-delay** on the Reverb. One guide's example is around 40 ms on a lead-vocal plate.
- **Use less on pads and background parts,** where a washier sound is fine.
- **Listen for clarity.** The lead should stay clear and the space should appear a moment later.
**Watch for:** a pre-delay so long that you hear a separate echo.

### 55. Decay too long for the tempo
**Why:** long tails in a busy arrangement pile up and blur the groove.
**Try this:**
- **Start short for depth:** roughly 0.3-0.8 s for a room, or 1.2-2.5 s for a plate or hall, as guides suggest.
- **Match the tempo.** A 4-second decay at 120 BPM blurs a mix.
- **Let the tail fade before the next phrase** when you can.
**Watch for:** long decay used to cover weak parts.

### 56. Too many different reverbs
**Why:** eight different rooms make the mix feel like a collage instead of one performance.
**Try this:**
- **Use two or three shared spaces.** A common setup is one short room and one longer plate or hall, both at 100% wet, with send levels doing the balancing.
- **Start with what you have.** Your A Reverb return can be the plate or hall. If your Live edition lets you add another return, make it a short room.
**Watch for:** switching to a new reverb for every track.

### 57. Delays muddy or invisible on phones
**Why:** low content in delays muddies the mix, and on small speakers the repeats can disappear.
**Try this:**
- **Filter the delay return.** Live's Delay has a filter section, or use Channel EQ on the return with the high-pass on.
- **Lower the feedback** if the repeats pile up.
- **Test on a phone speaker.**
**Watch for:** repeats that fight the vocal. Duck or shorten them.

### 58. No front-to-back depth
**Why:** when everything is equally near, the mix feels flat.
**Try this:**
- **Vary the send levels.** More reverb on a sound pushes it back. Less keeps it close.
- **Use pre-delay to place sounds.** A longer pre-delay keeps a sound near the front, and little or none pushes it back.
- **Roll off some highs** on reverb for farther sounds. Distant sounds are usually duller.
**Watch for:** putting reverb on everything, which flattens depth again.

### 59. Hidden reverb in presets
**Why:** some instrument presets, amp simulators and channel strips have reverb built in and switched on.
**Try this:**
- **Mute your two return tracks** and listen. If you still hear reverb, it is coming from inside a device.
- **Open the device chains** on the offending tracks and switch it off.
**Watch for:** buying or downloading presets and never checking what's inside.

### 60. Constant wash
**Why:** reverb on everything all the time tires the ear and takes away contrast.
**Try this:**
- **Automate the send.** Less in busy sections, more in sparse ones.
- **Shorten tails** in quieter or faster parts.
- **Duck the reverb** with a Compressor on the return, sidechained from the vocal, with a release of 200 ms or more so it doesn't pump.
- **Dampen the highs** on the return if it feels harsh.
**Watch for:** a mix that feels "tired" after thirty seconds. That points to too much total reverb.

---

## G. Stereo, width and phase (pain points 61-70)

The idea running through this group: width comes from real differences between the left and right sides, and tricks that fake it tend to collapse in mono. Many phones, small speakers and Bluetooth speakers play near-mono, so a mix that survives mono works for more people.

### The width routine
1. **Mono check first.** Put a Utility on the Main track and switch Mono on while you listen. Remember to switch it off, or remove it, before you export.
2. **Pan in balanced pairs,** with lows and lead sounds in the center.
3. **Build width from real differences:** doubled parts, different sounds left and right, stereo reverb on a return.
4. **Check mono again** after each widening move.

### 61. Everything panned center
**Why:** sounds fight for the same spot, so the mix feels narrow and cluttered.
**Try this:**
- **Keep the anchors in the center:** kick, snare, bass and the lead vocal.
- **Move supporting parts** left and right, such as guitars, keys, pads, percussion and backing vocals.
- **Pan in pairs** so the sides stay balanced. If one part goes left, a contrasting part goes right.
- **Rule of thumb from guides:** lows in the center, mids spread, highs toward the sides.
**Watch for:** panning a sound and forgetting to check it in mono.

### 62. Everything wide
**Why:** if every sound is wide, the center empties out and nothing feels solid.
**Try this:**
- **Decide what stays centered,** then let the rest widen around it.
- **Use contrast.** A narrow verse against a wide chorus makes the chorus feel bigger.
- **Skip stereo wideners** on things that carry the mix.
**Watch for:** widening as the fix for a mix that feels small. The cause is often clutter or level.

### 63. Fake widening
**Why:** wideners, phase tricks and very short delays create width by making the two sides different in timing or phase. In mono, those differences cancel, and the sound can lose several dB or disappear.
**Try this:**
- **Build width from real differences.** Record or program two separate takes, one per side. Use different sounds or notes on each side. Send a mono sound to a stereo reverb on a return.
- **Keep the dry sound centered** and let the reverb or delay carry the width.
- **Use Utility's Width with care.** Above 100% it widens, but it can lower the level in mono. Compare in mono every time.
**Watch for:** a "wide" sound that gets weaker when you press Mono.

### 64. Mix falls apart in mono
**Why:** phase differences between the sides cancel when they're added together.
**Try this:**
- **Compare in mono** at the loudest section. Listen for level drops, disappearing parts, hollow tone and reverb that turns to noise.
- **Find the culprit** by muting parts one by one while in mono.
- **Fix it at the source,** using the tricks in 63, 65 and 66.
**Watch for:** fixing mono by making everything narrower. Fix the specific parts that collapse.

### 65. Phase cancellation from layering
**Why:** two similar sounds that start slightly apart can thin each other out.
**Try this:**
- **Flip polarity.** In Utility, click both **Ø L and Ø R** on one layer, then compare.
- **Align the start times** of the two layers.
- **Separate them by role,** for example one layer for the low end and one for the top, with Channel EQ.
- **Check mono.** Cancellation shows up quickly there.
**Watch for:** a flip that fixes the low end and hurts the top. Try both ways.

### 66. Stereo delays and chorus lose level in mono
**Why:** these effects create differences between left and right, which cancel when summed.
**Try this:**
- **Put them on a return** so the dry sound stays centered.
- **Shorten very short stereo delays,** since delays under about 10 ms behave like phase tricks. A real double-track is safer.
- **Mono-check** any stereo effect after you set it.
**Watch for:** a lush stereo delay that vanishes on a phone.

### 67. Width in the lows
**Why:** low frequencies are the least stable part of a stereo mix and cancel most easily.
**Try this:**
- **Utility's Bass Mono** makes everything below its set frequency mono. Guides suggest keeping lows mono below roughly 100-150 Hz.
- **Skip widening below about 300 Hz,** where widening messes with the balance and adds phase problems.
- **Do this on wide synths and pads,** not only on the bass.
**Watch for:** a mix whose low end changes when you press Mono.

### 68. Extreme panning
**Why:** a sound panned all the way to one side can disappear on a single earbud, and it can weaken in mono.
**Try this:**
- **Stop short of the edge** for parts that need to be heard, and use full pans only where it helps.
- **Pair hard-panned parts** with a counterpart on the other side, such as two separate guitar takes.
- **Listen on one earbud** as a quick test.
**Watch for:** a hard pan that puts an important part in one ear only.

### 69. Never checking mono
**Why:** you can't fix what you don't hear.
**Try this:**
- **Make it a habit.** Press Mono at the start of a mix, after big changes, and at the end.
- **Use a Utility on the Main track** with Mono on and off for A/B.
- **Listen for the same four signs** as in 64.
**Watch for:** forgetting the Utility on the Main track when you export.

### 70. Too many pan positions
**Why:** the ear can distinguish only a few positions at once, so lots of slightly different pans blur together.
**Try this:**
- **Use a few clear positions:** center, moderately left and right, and wide.
- **Add movement without clutter.** Auto Pan on hats or shakers gives motion while kick and snare stay in the middle.
- **Automate pans** in sections that need life.
**Watch for:** moving everything a little. Clear choices sound better.

---

## H. Levels, headroom and loudness (pain points 71-80)

Loudness targets vary by source and by streaming platform, and some engineers argue they matter less than people think. The numbers below are common starting points, so check each platform's current guidance before you rely on them.

### The level routine
1. **Get clean levels in.** Recorded or imported sounds should peak comfortably below the top of the meter.
2. **Gain-stage each track** before plugins that react to level.
3. **Balance with faders** near their middle range.
4. **Check the Main track's peaks** on the loudest section.
5. **Leave loudness for the end.**

### 71. Recording too hot
**Why:** digital clipping is harsh, and once it is recorded it can't be repaired.
**Try this:**
- **Set input gain** so the loudest moment peaks around -10 to -8 dBFS at the input, as one guide suggests, and leave the top of the meter alone.
- **Watch the peak number** above each track's meter. Clicking it resets it.
- **Re-record** if the take clipped. Utility can lower the level but can't undo clipping.
**Watch for:** setting the level during a quiet rehearsal and then singing louder.

### 72. Poor gain staging into plugins
**Why:** many plugins, especially ones modelled on analog gear, behave differently depending on the level they receive. Compressor thresholds also depend on it.
**Try this:**
- **Aim for a moderate level going in.** One guide suggests about -18 dBFS average for many plugins. Others use different figures, so treat it as a guide.
- **Trim with Utility's Gain** at the start of a chain, or use clip gain, so the next device receives a sensible level.
- **Match levels out** with Channel EQ's Output, the Compressor's Out or Makeup, and OTT's In Gain and Out Gain.
**Watch for:** fixing a hot signal at the end of the chain. Fix it before it hits the plugins.

### 73. Faders at extremes
**Why:** a fader far above or below zero usually means the level problem is upstream.
**Try this:**
- **Keep faders within about 5 dB of zero** as a rule of thumb.
- **Adjust the source level** with clip gain or Utility, then set the fader.
- **Group tracks** and move the group fader for overall balance.
**Watch for:** a lead track fader pushed to the top because the rest of the mix is too loud.

### 74. No headroom on the master
**Why:** a mix that peaks near the top has nothing left for mastering, or for any device that adds level.
**Try this:**
- **Aim for Main peaks around -6 dBFS** before mastering, with average levels well below that (guides suggest around -12 to -10 dBFS).
- **Read the meter on the loudest section,** not the intro.
- **A note on your template:** in your screenshots the Main fader reads -6.0 dB. That is one way to leave headroom, and it also lowers the level of your exported file by the same amount.
**Watch for:** fixing peaks by pulling the Main fader while individual tracks are still clipping.

### 75. Chasing loudness while mixing
**Why:** loudness is decided in mastering, and pushing it early costs punch and clarity.
**Try this:**
- **Balance first,** loudness later.
- **If you want a loudness meter,** the free version of a meter plugin such as Youlean Loudness Meter works in Live (Live Intro has no loudness meter of its own).
- **Compare against a reference track at equal volume** instead of judging by how loud yours is.
**Watch for:** a limiter left on the Main to make the mix feel finished.

### 76. Over-limiting the master
**Why:** streaming services adjust volume, so a very loud master gets turned down and you keep the squashed dynamics.
**Try this:**
- **Use less limiting.** One guide notes that a master pushed to about -8 LUFS on Spotify simply gets turned down by roughly 6 dB, with no loudness benefit.
- **Push loudness until the attack starts to flatten, then back off.**
- **Compare limited and unlimited versions** at equal volume.
**Watch for:** a master that sounds loud but feels lifeless.

### 77. Not knowing streaming targets
**Why:** platforms normalize loudness differently, and knowing the numbers stops you guessing.
**Try this:**
- **Common starting points from a recent guide:** about -14 LUFS integrated for Spotify, YouTube and TikTok, and about -16 for Apple Music, with true peak around -1 dBTP.
- **Know that sources disagree.** Some recommend more true-peak headroom for loud masters, and some engineers question whether hitting exact targets matters.
- **Check each platform's current documentation** before you finalize.
**Watch for:** treating any of these figures as a rule instead of a starting point.

### 78. Master-bus processing left on
**Why:** a leftover limiter or effect on the Main changes how everything sounds and can hide problems.
**Try this:**
- **Open the Main track's device chain** and look at what's on it.
- **Bypass everything** and compare at equal volume.
- **Keep only what you can explain,** such as a gentle compressor doing 1-2 dB of reduction, or nothing at all.
**Watch for:** a default limiter that came with a template and never got removed.

### 79. Sub buildup limits loudness
**Why:** excess sub energy triggers a limiter early and stops the whole mix from getting loud.
**Try this:**
- **Cut the sub** from sounds that don't need it (see A3 and A8).
- **Keep lows mono** with Utility's Bass Mono (see G67).
- **Test on a small speaker.** If the bass disappears there, the low end may be all sub.
**Watch for:** boosting the low end to make a track feel bigger without checking what it does to the peaks.

### 80. Handing a hot mix to mastering
**Why:** a mastering stage needs room to work, and a limited mix takes away options.
**Try this:**
- **Export with peaks around -6 dBFS,** no limiter on the Main, and the dynamic range intact.
- **Export at a high quality format.** 24-bit WAV is the usual choice.
- **Keep a separate limited version** if you want to preview loudness.
**Watch for:** sending a file with the Utility Mono check still on, or a preview limiter still active.

---

## I. Monitoring and workflow (pain points 81-90)

A reference track works like a tuning fork. It doesn't tell you what to play. It shows you where your ears have drifted.

### The translation routine
1. **Bounce the mix** and listen to the file, not the session.
2. **Phone speaker** (not Bluetooth): are the vocals and bass line still clear? Muddy vocals point to too much reverb.
3. **Laptop speakers:** mid-range buildup shows up here.
4. **Car or earbuds:** a bass that swells in the car usually has too much low end.
5. **Mono:** use Utility's Mono button.
6. **Quietly:** turn it down until it's barely audible. Extreme lows and highs fade at low volume, so this shows whether the balance still holds.
7. **Write notes,** fix the biggest issues, and check again.

### 81. Mixing in solo
**Why:** a sound made to be great alone often clashes with everything else.
**Try this:**
- **Make decisions with everything playing.** Solo only to find a specific problem, like a click or a ring.
- **If you can't hear the part you're working on,** raise its fader until it's audible, make the change, then rebalance.
- **Return to the full mix** after every solo session.
**Watch for:** a vocal or bass that sounds perfect in solo and disappears in the mix.

### 82. Monitoring too loud
**Why:** louder always sounds better and more exciting, which hides problems and tires your ears faster.
**Try this:**
- **Mix at moderate volume.** Guides suggest roughly 75-85 dB SPL, and closer to 73-76 in a small room. A free SPL meter app on your phone gives a rough check.
- **Turn it up briefly** for a check, then bring it back down.
- **If your ears feel "warmed up,"** you were probably mixing too loud.
**Watch for:** volume creeping up as your ears tire.

### 83. Ear fatigue
**Why:** tired ears lose high-frequency detail and judge balance poorly, and you make bigger EQ moves to compensate.
**Try this:**
- **Take a break** every 45-60 minutes, even a few minutes.
- **Switch listening systems** when things start to sound fuzzy.
- **Sleep on it,** and listen the next day with fresh ears before you finalize.
**Watch for:** heavy EQ moves late in a long session. Undo and recheck them after a break.

### 84. One listening system
**Why:** every speaker and headphone has its own bias, so a mix that sounds right on one can sound wrong elsewhere.
**Try this:**
- **Use the translation routine above** at the end of each session.
- **Listen for the big mistakes,** like a vocal too quiet, bass too heavy, a snare too bright, or reverb too washy.
- **Don't chase perfection on every system.** A few clear differences are enough.
**Watch for:** fixing the mix for one speaker and breaking it on the others.

### 85. No reference tracks
**Why:** without a comparison, tone, width and balance drift away from what you intended.
**Try this:**
- **Pick two or three finished tracks** in your genre that you trust.
- **Put a reference on its own track** in the session and switch between it and your mix often.
- **Check the reference clip's Warp button** so Live isn't time-stretching it.
- **Compare specific things:** low end, vocal level, brightness, width, and how loud the drums are.
**Watch for:** copying a reference blindly. Use it to hear what's missing, then decide for yourself.

### 86. References at different volume
**Why:** the louder one almost always sounds better, whatever its quality.
**Try this:**
- **Match volumes** before you compare, using **Utility's Gain** on the reference track.
- **Match by ear, then check** the two again with your eyes closed if you can.
- **Recheck after any change** to your mix's level.
**Watch for:** a reference a few dB louder that makes your mix sound weak.

### 87. Headphones exaggerate lows and highs
**Why:** headphones can hype or hide bass and treble, which can leave you with a scooped midrange or a weak low end.
**Try this:**
- **Learn your headphones** by listening to your reference tracks on them.
- **Cross-check on other systems,** such as speakers, earbuds and the car.
- **Use their strengths.** Headphones are good for hearing reverb tails and phase problems, so solo the returns and listen there.
- **Take breaks.** Headphones press sound straight into your ears and tire them quickly.
**Watch for:** mixing loud on headphones because it sounds great.

### 88. The room lies
**Why:** an untreated room adds and removes frequencies, especially in the bass, so what you hear isn't quite what's in the file.
**Try this:**
- **Learn your room** by playing reference tracks in it and noticing what they sound like there.
- **Cross-check on headphones and other systems** before you trust a low-end decision.
- **Treat it as a long-term project.** Acoustic improvements help, but they aren't required to start.
**Watch for:** boosting or cutting the low end to fix something that is really your room.

### 89. Plugins before balance
**Why:** plugins can't fix a balance problem, and they add up fast.
**Try this:**
- **Rebuild with faders and panning only.** Bypass your rack and other processing.
- **Get the lead, kick and bass, and snare sitting right.**
- **Add processing back one device at a time,** and compare with bypass.
**Watch for:** stacking EQs and compressors on a track that only needs a fader move.

### 90. Endless tweaking
**Why:** small changes stop improving the mix, and tired ears make them worse.
**Try this:**
- **Set a limit.** Decide how many passes you'll do before you stop.
- **Save versions.** Use Save Live Set As with numbers, so you can go back.
- **Take a break or sleep on it,** then decide with fresh ears.
- **Get feedback** from someone you trust.
**Watch for:** undoing good decisions in search of perfect.

---

## J. Digital-specific and finishing (pain points 91-100)

### The digital health routine
1. **Watch the CPU meter** in Live's top bar while the session plays.
2. **Listen for clicks, crackles and metallic highs** on a loud section.
3. **Freeze heavy tracks** you're finished with.
4. **Export, then listen to the file from start to finish.**

### 91. Digital clipping anywhere in the chain
**Why:** digital clipping creates harsh harmonics that EQ can't remove, and it can happen inside a chain as well as at the master.
**Try this:**
- **Turn devices off one at a time** on a track that crackles on loud passages, and listen for where the harshness stops.
- **Check each device's output level,** not just the master.
- **Lower the level going into devices that distort** (saturators, and some plugins).
- **Know the limits of the meter.** Live is generally forgiving of levels above the top inside its own chain, but hot signals still distort nonlinear devices and can clip at the output or export.
**Watch for:** fixing the master fader while a track earlier in the chain is the real cause.

### 92. Aliasing from saturation and distortion
**Why:** distortion creates harmonics above what digital audio can represent, and they fold back into the audible range as metallic, inharmonic noise, often on cymbals and high notes.
**Try this:**
- **Look for a "Hi-Quality" or oversampling option** on distortion and saturation devices, and try it where available.
- **Use less drive.** Heavy drive on bright material makes it worse.
- **Judge it in the full mix.** One guide notes that if you can't hear the artifact in the whole mix, oversampling probably won't help.
**Watch for:** blaming the wrong device. Compressors with extremely fast attack and release can also add artifacts.

### 93. Oversampling on everything
**Why:** oversampling multiplies CPU use, so turning it on everywhere slows the session and can add latency.
**Try this:**
- **Use it only on the devices that need it,** such as a heavy distortion or a clipper.
- **Freeze or render** tracks with heavy processing.
- **Use a lower setting first** and only go higher if you hear a difference.
**Watch for:** high oversampling on many tracks "just in case."

### 94. CPU overload, crackles and dropouts
**Why:** the computer can't process audio fast enough.
**Try this:**
- **Freeze tracks** you're done with (right-click the track and choose Freeze Track).
- **Raise the buffer size** in Settings → Audio while mixing.
- **Close other apps** and check that your disk isn't full.
- **Keep the rack bypassed** when you don't need it. An off device uses very little CPU.
**Watch for:** high oversampling or many instances of heavy plugins.

### 95. Clicks while recording
**Why:** the buffer is too small for the load, so audio arrives late.
**Try this:**
- **Raise the buffer size** if you hear clicks on transients.
- **Reduce the plugin count** on tracks while recording.
- **Balance the trade-off.** A small buffer gives low latency for recording, and a larger one is safer for mixing.
**Watch for:** leaving a huge buffer on during recording. You'll hear the delay in your headphones.

### 96. Phase issues from oversampling and latency
**Why:** processing that adds delay can leave the wet and dry signals slightly out of step.
**Try this:**
- **Keep Delay Compensation on** (in Live's Options menu).
- **If a return sounds phasey,** use the effect as an insert with a Dry/Wet control instead of a send.
- **Compare on and off** with Utility's Mono button.
**Watch for:** turning Delay Compensation off to fix a monitoring delay, and forgetting to turn it back on.

### 97. Inter-sample peaks after export
**Why:** the reconstructed waveform between samples can rise above 0 dBFS, and lossy encoding can add to it. That can distort on a listener's device.
**Try this:**
- **Leave a small ceiling.** A common choice is around -1 dBFS for true peak, and some sources suggest more for very loud masters.
- **Use a limiter's true-peak mode** if it has one. Engineers disagree on whether it costs too much punch, so compare by ear.
- **Listen to a loud section** of the exported file on a phone.
**Watch for:** a master that peaks right at the top.

### 98. A static mix
**Why:** levels, panning and effects that never change make a mix feel flat and robotic.
**Try this:**
- **Automate volume** for verses and choruses, and for individual words in a vocal.
- **Automate sends** for reverb and delay.
- **Automate filters and pans** for builds and movement.
- **In Live,** press A to show automation and B for draw mode.
**Watch for:** automation that competes with the arrangement instead of supporting it.

### 99. Sample-rate mismatch
**Why:** files at a different rate than the session get converted, and poor conversion can add artifacts.
**Try this:**
- **Check the rate** in Live's top bar (yours shows 44.1 kHz) and in Settings → Audio.
- **Keep source files at the same rate where you can.**
- **Listen for metallic artifacts** on imported material if the rates differ.
**Watch for:** changing the session rate partway through a project.

### 100. Not checking the final bounce
**Why:** the exported file is what people hear, and it can differ from the session.
**Try this:**
- **Check the export dialog:** the whole song is covered (Live renders the loop or selection area if you have one), Convert to Mono is off, and the format and bit depth are what you intend.
- **Listen from start to finish,** including the fades and the very end.
- **Run the translation routine** from group I: phone, laptop, car or earbuds, mono, and quiet.
- **Remove any check tools** such as a Utility with Mono on the Main track.
**Watch for:** sending a file you haven't listened to.

---

## What's next for this library
All ten groups are written. Ways to grow it:
- **Rack recipes:** saved variations of your FX rack for drums, vocals and bass.
- **Genre pages:** how the same problems look in your genres.
- **A one-page cheat sheet** to keep open while mixing.
