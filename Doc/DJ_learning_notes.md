# DJ Learning Notes
> Source: Numark Party Mix user guide + session notes
> Date: 2026-04-25

---

## 1. Beat → Bar → Phrase

```
Beat:    1   2   3   4  |  1   2   3   4  |  1   2   3   4  |  1   2   3   4
         └───────────────┘  └───────────────┘  └───────────────┘  └───────────────┘
Bar:           Bar 1               Bar 2               Bar 3               Bar 4
         └─────────────────────────────────────────────────────────────────────────┘
Phrase:                                  1 Phrase (16 beats)
```

- 1 bar = 4 beats. Beat 1 = downbeat.
- 1 phrase = 4 bars = 16 beats.
- DJ actions (transitions, drops) must happen on phrase boundaries — otherwise the beat structures of two songs misalign.

---

## 2. DJ-Friendly Song Structure

```
INTRO (64) → BREAKDOWN (short) → BUILD (short) → DROP (64) → BREAKDOWN (short) → BUILD (short) → OUTRO (64)
```

| Section   | Length     | Purpose |
|-----------|------------|---------|
| INTRO     | 64 beats   | Drums only, no melody — space for DJ to mix in |
| BREAKDOWN | Short      | Energy drops, drums disappear — crowd breathes |
| BUILD     | Short      | Tension rises — filter sweeps, snare rolls signal the drop |
| DROP      | 64 beats   | Full energy, all elements in |
| OUTRO     | 64 beats   | Mirror of intro — elements drop out — space to mix out |

### The Mixing Window
```
Song A OUTRO  ↔  Song B INTRO
  (64 beats)       (64 beats)
```
Both sections are "empty" enough that two songs playing simultaneously don't clash. This is the mixing zone — designed into the structure by default.

---

## 3. Four Core DJ Skills

All four are fully practicable on the Party Mix.

1. **Track selection & ordering** — BPM proximity, key compatibility, energy arc
2. **Beat matching** — Align Beat 1 of both tracks; make transitions at phrase boundaries
3. **EQ transitions** — Cut Low EQ on incoming track to prevent bass clash during overlap
4. **Timing** — Push the crossfader at the correct phrase boundary

> Effects (Echo, Reverb, Flanger) are decorative. Many skilled DJs rarely use them. Overuse sounds messy.

---

## 4. Filter — The Real Missing Feature on Party Mix

| Tool | Party Mix | Effect |
|------|-----------|--------|
| High EQ | ✓ | Adjusts treble gain |
| Low EQ | ✓ | Adjusts bass gain — limited cut depth |
| Filter (HPF/LPF) | ✗ | Fully removes frequencies above/below cutoff |

**Why Filter matters more than Echo:**
- EQ faders adjust gain within fixed bands — cannot fully cut low frequencies.
- A Low Pass Filter (LPF) can sweep the cutoff down, letting the new track "emerge from darkness" gradually — standard technique in house/techno transitions.
- Workaround on Party Mix: use Serato's software FX, but no hardware knob = less intuitive.

---

## 5. Controller Comparison

| | Party Mix | DDJ-FLX2 | Mixtrack Plat FX | DDJ-400 | DDJ-FLX4 |
|---|---|---|---|---|---|
| New price | ~$99 | ~$189 | ~$279 | Discontinued | ~$329 |
| Used price | ~$50–80 | ~$120–150 | ~$130–170 | ~$150–200 | ~$200–250 |
| Software | Serato Lite | Rekordbox + Serato + djay | Serato Lite | Rekordbox full | Rekordbox + Serato + Traktor + djay |
| Jog wheel | Small, no display | Small, no display | 6", color display | 5", no display | 5", no display |
| Decks | 2 | 2 | 4 (Pro required) | 2 | 2 |
| Pads/deck | 4 | 8 | 8 | 8 | 8 |
| EQ | 2-band, no filter | 3-band + CFX filter | 3-band + filter | 3-band + filter | 3-band + filter |
| Gain knob | Yes | No | Yes | Yes | Yes |
| Effects | Basic pad FX | Smart CFX | FX paddle + 6 FX | Beat FX | Beat FX + Smart CFX |
| Mic input | No | No | Yes (1/4") | Yes (1/4") | Yes (1/4") |
| Master output | RCA | 3.5mm | RCA | RCA | RCA |
| Headphone | 3.5mm | 3.5mm | 3.5mm + 6.35mm | 3.5mm | 3.5mm |
| USB | USB-A | USB-C | USB-B | USB-B | USB-C |
| Bluetooth | No | Yes | No | No | Yes |
| Club layout | No | Basic | No | Yes | Yes |

### Selection Logic

| Goal | Recommendation |
|------|----------------|
| Budget (used) | DDJ-400 ~$150–200 — Pioneer layout, Rekordbox full, Filter included. Risk: discontinued, no warranty. Watch for overpriced listings. |
| Best new value | DDJ-FLX2 ~$189 — Fixes Filter gap, dual-software, USB-C. Club layout is only "basic". |
| Long-term device | DDJ-FLX4 ~$329 — Pioneer standard layout + Filter + 3 software licenses + USB-C. |
| Avoid | Mixtrack Plat FX — $279 but Serato Lite only + no club layout. Weak value vs FLX4 used. |

### Rekordbox full vs Serato Lite
- Serato Lite: 2 decks max, no Flip, no DVS.
- Rekordbox full (DDJ-400 / FLX4): no such limits + USB export format compatible with club CDJ setups.

---

## 6. Learning Resources

| Resource | Type | Notes |
|---|---|---|
| Numark Party Mix User Guide v1.1 | Hardware manual | Reference for Cue/PFL, Jog Wheel, EQ controls |
| DJ Carlo Atendido — YouTube | Free video | Good quality, worth watching |
| DJ Carlo Atendido — Sellfy paid course | Paid ($50) | **Not recommended** — identical content to his free YouTube videos |
| "How To DJ For Beginners 2026" (YouTube) | Free video | Primary learning reference |
| Club Ready DJ School / Ross Palmer (Udemy) | Paid course | Recommended by Reddit r/Beatmatch — buy on sale (~$13–20) |

---

## 7. Six-Stage Learning Path

### Stage 1 — Ear Training (Foundation)
- Count the kick drum out loud: **1-2-3-4 / 1-2-3-4...**
- Tap once with your other hand every 4 bars (= every 16 beats = 1 phrase)
- **Hide the waveform** in Serato — train your ears, not your eyes
- Feel where the music changes — changes always land on phrase boundaries

### Stage 2 — Jog Wheel Control
- Think of the jog wheel as a **clock face**
- Quarter turn / half turn = muscle memory for pitch correction
- Practice method: load the same track on both decks, deliberately offset the beat, correct using only your ears and jog wheel — no Sync

#### How Master Output and Headphones Work Together

The crossfader controls what the audience hears through the Master Output:

```
Crossfader full left  → Master outputs Deck 1 only
Crossfader full right → Master outputs Deck 2 only
Crossfader center     → Master outputs both
```

In a real mix, the audience hears Master Output through the speakers. You never want Deck 2 bleeding into Master while the audience is still listening to Deck 1 — that's two songs clashing in public.

Headphones run on the Cue Output, which is independent of Master. This lets you privately monitor Deck 2 while the audience hears Deck 1 only:

```
Audience hears:  Deck 1 only  (Master)
You hear:        Deck 1 (left ear) + Deck 2 (right ear)  (Cue Mix)
```

The **Cue Mix knob** on the Party Mix controls this ratio — turn toward CUE to focus on the incoming track, turn toward PGM to hear the Master.

#### Correct Practice Workflow
1. Push crossfader fully left — Deck 1 plays to Master
2. Press the PFL/Cue button on Deck 2
3. Put on headphones, adjust the Cue Mix knob
4. Listen to both tracks in your headphones simultaneously
5. Use the jog wheel to align the beats
6. Once aligned, push the crossfader across to mix in

### Stage 3 — EQ Swap
- Cut the Low EQ on the incoming track → bring up the fader → gradually swap the bass between tracks
- After every transition: **reset all EQs to the 12 o'clock position** — make this a habit

### Stage 4 — Phrasing
- Always start the mix-in on **Beat 1** of a phrase
- Standard mixing window: **32 or 64 beats**
- "On phrase" mixing = transitions that feel natural and musical

### Stage 5 — Mixing in Key
- Use the **Camelot Wheel** to select harmonically compatible tracks
- Apply this after Stage 3 is solid

### Stage 6 — Live Mix Practice
- Mix continuously without pre-planning
- Record yourself and listen back critically

---

## 8. Core Practice Techniques

### EQ Swap — Step by Step
1. Cut the Low EQ on the incoming track
2. Bring up the Channel Fader to introduce the track
3. Gradually swap the bass: lower the outgoing track's Low EQ while raising the incoming track's Low EQ
4. Once the transition is complete, reset all EQs on both decks to 12 o'clock

### Hide the Waveform
Turn off or minimize the waveform display in Serato. Force yourself to judge the beat and song structure by ear alone.
Relying on the visual waveform delays ear development — this is the most important habit to build as a beginner.

---

## 9. 1st_Song.wav — Structure Analysis

**Info:** Duration 1:37 | BPM 125 | Type: short loop / sample pack track

### Phrase Map (every 16 beats ≈ every 8 seconds)

| Phrase | Timestamp |
|---|---|
| 1 | 0:00 |
| 2 | 0:08 |
| 3 | 0:16 |
| 4 | 0:24 |
| 5 | 0:31 |
| 6 | 0:39 |
| 7 | 0:46 |
| 8 | 0:54 |
| 9 | 1:02 |
| 10 | 1:10 |
| 11 | 1:17 |
| 12 | 1:25 |

### Structure Map

| Section | Time | Waveform Characteristics |
|---|---|---|
| INTRO | 0:00–0:14 | Dense periodic spikes, kick drum clearly visible |
| BREAKDOWN | 0:14–0:30 | Waveform thins out, energy drops sharply |
| BUILD UP | 0:30–0:46 | Gradually densifies, tension builds |
| DROP | 0:46–1:14 | Densest and loudest, all elements in |
| OUTRO | 1:14–1:37 | Gradually sparse, mix-out window |

**Visualizations:**
- [Energy Structure Map](./energy_map.html)
- [Waveform Structure Map](./waveform_structure.html)

---

## 10. Next Actions

1. Play 1st_Song.wav, count 1-2-3-4, and feel the Drop arrive at 0:46
2. Upload a full-length track (3–5 min) for deeper structure analysis
3. Load the same track on both decks in Serato — no Sync, correct with jog wheel only
4. Paid course: wait for Ross Palmer (Udemy) to go on sale (~$13–20)
