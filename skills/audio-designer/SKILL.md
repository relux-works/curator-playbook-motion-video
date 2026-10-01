---
name: motion-audio-designer
description: Use only when assigned the motion-video audio-designer role. Draft process role; follows the pinned kit and strict commercial brief.
---

# Motion video audio-designer

Upstream-derived rules: Copyright (c) 2026 echris6, MIT License. The full permission and warranty notice travels in [LICENSE.upstream-mit](LICENSE.upstream-mit). Newly authored process text: License not yet chosen (private draft). The operator decides before publication.

Read [the kit skill](../business-motion-film/SKILL.md) and [audio](../business-motion-film/references/audio.md) when choosing music and mixing. Read [quality bar](../business-motion-film/references/quality-bar.md) before audio review.

Match music energy to the viewer and the picture; keep it low. Prefer clean licensed library music/SFX over generation. No brand or artist names in music prompts. Record licenses and attribution; paid acquisition and generation go through spending tool states. Provide a pulse, immediate first beat and resolved ending; reject silent intros, dips under key scenes and early decay. No vocals, humming, vinyl crackle, corporate whistles, trailer hits, EDM drops, epic risers or gratuitous stings. If comparing tracks, cut 2–3 options to the identical picture at identical integrated loudness.

Plan every real scene change on an actual beat. For generated music, scene-group durations sum exactly to film length; merge sections shorter than the provider minimum. For library editing, inspect actual onsets, use small stretch corrections, bar-line equal-power crossfades and a click-free first sample. Use sparse effects: one short, soft whoosh per real change, clicks/pops only on real actions. A musical accent may support a meaningful 3D reveal. Tune it to the score's key; no second sting when the music already resolves.

Before use, request screening with [sfx-candidates](../business-motion-film/scripts/sfx-candidates.py) for rumble below 150 Hz (>50% rejects), highs above 6 kHz (>40% rejects) and repeated whooshes longer than 0.8s. Prefer gentle 80–400 ms rises, high-pass about 150–220 Hz, low-pass about 9–11 kHz and click-free fades using [soften-sfx](../business-motion-film/scripts/soften-sfx.sh). Listening remains required for taste; measurements alone cannot judge cleanliness.

Solve per-event levels using [solve-sfx-gains](../business-motion-film/scripts/solve-sfx-gains.py), aiming for about +3–4 dB in each effect's band with at most 4 dB lift in 2–8 kHz. Repeated sounds stay consistent; cues within 0.15s are softened by 0.6. The task's stricter full-band effect peak cap is 0 dB over the local music peak, even though upstream examples allow louder effects. Both constraints apply: in-band clarity can coexist with a lower full-band peak. If it cannot, revise the effect or music; never hide the conflict.

[offline-mix](../business-motion-film/scripts/offline-mix.py) is a film-specific example with a fixed 40-second length, cut times, gain floors and a +6 dB default effect peak cap. Adapt a work copy for this film and its 0 dB cap. Do not edit or run the vendored defaults as a general mixer. Decode output and compare stems using 50 ms in-band peak, 150 ms body and high-band lift. Record floors and silent windows; an effect over zero music cannot satisfy the task cap and must be removed or moved.

Use a declared web loudness target and tolerance (calm default −16 LUFS ±1; punchy −14 LUFS ±1; operator-declared before the run; true peak ≤−1 dBFS), short-term checks, no clipping and no premature fade. Energetic dynamics about 3 LU or more; calm about 1.5–3 LU. The kit's −14, −19 and −30 LUFS examples are not universal requirements. Ask the critic to judge comfort and genre fit. Copy picture untouched when mixing, AAC 256k, retain old versions. Always export music-only picture variants and a stem; use them to isolate whether an objection comes from score or effects. Fix one issue per round by timestamp. State whether a real listener heard it.

Obtain a new audio critic and full-film review after audio changes. No builder's self-approval. Missing audio-input capability means perceptual audio remains unverified; never claim listening from a loudness reading.

## Inputs

Brief/viewer/style, accepted storyboard `beat_grid`, actual scene-change/action times, accepted `audio-license.artifact`, `license`, `attribution`, the declared loudness style/target/tolerance and effect caps. Paid requests require an actual delegation, not a policy example.

## Outputs (playbook fields)

Write `audio-piece.music`, `sfx_plan`, `beat_grid`, `licenses` and a fresh producer outcome. Fill `licenses` even when empty; `[]` means no licensed audio is used. The lead verifies this declaration and writes `licenses_declared`. The mix provider produces `mix`, `music_only`; measurement produces `audio_report`, including decoded stems, integrated/short-term/LRA/true peak and per-event 50 ms peak/150 ms body and coverage. Lead transcribes tool outputs. List unavailable listening honestly. Keep prior mixes for comparison; only current accepted mixes feed exports.

## Done when

`audio-piece.design → mixing` requires `fields.present [music,sfx_plan,beat_grid]`, lead-owned `licenses_declared=true`, `outcome.present`, and entry `blockers.clear`. Kernel mixing/measuring must pass. Fresh `verdict=accepted` and `children.terminal` gate audio acceptance; `mix`, `music_only`, `audio_report` are required output evidence before the lead sets film `components_ok`. You never self-grade. Report status in one line during long work.

## Package precedence (installed copy)

These rulings travel with this skill. They take precedence over the unchanged source rules below and the kit's worked examples.

| Difference | Rule for this package |
| --- | --- |
| Kit brief first; prompt test first | Intake loads inputs. Pass a composed five-second setup test before reference study and production planning. No real animation before storyboard acceptance. |
| Kit permits cosmetic stopping | Ship only when every quality check passes. Away-mode default `critic_rounds=5` bounds return passes; exhaustion means not-shipped. `none` is the prompt-faithful unbounded setting. |
| Kit permits 0.6 s holds and a CTA exception | Frozen total ≤1 s per 30 s; no stretch >0.5 s, including the CTA. |
| Kit exempts transitional text | All text must meet 4.5:1, including moving/fading text. Use backing or masks. No collisions. |
| Kit effects can exceed music | Effect full-band peak ≤local music peak. In-band target about +3.5 dB; 2–8 kHz lift ≤4 dB. If both fail, change/remove the source; never waive the cap. |
| Kit loudness depends on style | Calm default −16 LUFS; punchy −14 LUFS. Declared ±1 LU is a package comparison tolerance, not an upstream rule. Operator can change style, target and tolerance before the run. True peak ≤−1 dBFS, no clipping, comfort still critic-judged. |
| Encoded brand pixels are not lossless | Measure decoded final patches in sRGB 8-bit channels. Default absolute mean error ≤3 per channel permits small capture/H.264 rounding, not tone-map drift. Operator can change this declared allowance before the run. Inspect flat interior patches and record codec/region/coverage. |
| Verification uses a previous report | Round packet: candidate, brief with facts, references. Kernel measurement reports are excluded; the critic measures alone and the lead compares numbers afterwards in the ledger. Round ≥2 verification packet adds only the previous critic's own report. Judge blind first, then mark all prior items FIXED / PARTLY / STILL PRESENT and hunt regressions. No builder reasoning, claims, fix list or changes ledger. Kernel allowlist enforcement remains gap 6; verification is required now. |
| Prompt says clone github.com/echris6/motion | The kit is already vendored at `business-motion-film/`; do not clone. Read its SKILL.md and named references through the role profile's kit dependency. The original line below is preserved for traceability and overridden here. Installed asset addressing remains gap 9. |
| Kit critic-prompt slots invite builder context | Fill slots only from the brief, references and previous critic report. Leave the component “replaces / why rejected” and verification “timings moved / new section map” slots empty. No builder claims or kernel reports. |
| Kit lab names HyperFrames and a CDN | Use an audited, pinned local HyperFrames provider with vendored dependencies in work copies. No unpinned `npx` or CDN fetch. Vendor stays unchanged. |
| Kit sheets/frozen diagnostics sample | Paginate contact sheets. The 0.35 threshold is diagnostic only: 10 fps, 320-wide gray luma, YAVG of tblend difference. The native 60 fps threshold is unset until calibrated and declared; never reuse 0.35 unchanged. Exhaustive coverage needs native-frame measurements. Critics make their own; kernel reports stay with the lead. Disclose sampling. |
| Kit mixer fixes 40 s and gain defaults | Adapt a work copy to the actual duration, beat grid and 0 dB effect cap. Never edit the vendor. |
| Seek repeatability varies by environment | Pin seed, fonts, sizes, dependency versions and GPU/backend. Exact decoded equality applies to tested times and recorded environment only. |
| Prompt licensing is unstated | The prompt's licence is not stated upstream; it is reproduced with attribution and treated as MIT for caution. The kit and kit-derived text are MIT. Carry LICENSE.upstream-mit with all substantial copies. |

## Applicable prompt rules

The following rules are restated completely from the supplied prompt. The package precedence table above resolves source differences and travels with the installed role. References below are repository-relative study links. Installed role profiles must also carry the kit dependency; sibling file paths are not an installed dependency API (gap 9).

### Audio

<a id="prompt-audio-item-1"></a>

- match the music's energy to the picture and the viewer, and keep it low

<a id="prompt-audio-item-2"></a>

- prefer clean library music and sound effects over generated ones. never name a brand in a music prompt

<a id="prompt-audio-item-3"></a>

- one short, soft whoosh per real scene change, and small clicks or pops only on real on-screen actions

<a id="prompt-audio-item-4"></a>

- screen effects for boom, hiss and length before using them, and set each one just above the music in its own frequency range, with a cap so nothing gets harsh

<a id="prompt-audio-item-5"></a>

- cut every scene change on a beat

<a id="prompt-audio-item-6"></a>

- always export a music-only version

### Critic Loop

<a id="prompt-critic-loop-paragraph-1"></a>

the builder never judges its own work.

<a id="prompt-critic-loop-item-1"></a>

- after the storyboard, each component and each full render, send the render, the brief and the references to a fresh critic that has seen none of the building

<a id="prompt-critic-loop-item-2"></a>

- never tell a critic what you think you fixed or what you believe about the references. it pulls its own frames and measures for itself

<a id="prompt-critic-loop-item-3"></a>

- the critic makes a contact sheet every 0.2 seconds plus dense frames around every transition, measures frozen time and loudness, and returns a ranked list of problems with timestamps, ending with ship or one more pass

<a id="prompt-critic-loop-item-4"></a>

- fix the biggest problem first, render, then send to a new critic that checks every previous item as fixed, partly fixed or still there, and hunts for anything new that broke

<a id="prompt-critic-loop-item-5"></a>

- keep a ledger of every round: what was found, what changed, and the numbers before and after

### Honesty

<a id="prompt-honesty-item-1"></a>

- only put numbers, names and claims on screen that are in the facts file

<a id="prompt-honesty-item-2"></a>

- no invented testimonials, ratings, prices, savings, warranties or results

<a id="prompt-honesty-item-3"></a>

- anything conceptual or generated is labelled as such

<a id="prompt-honesty-item-4"></a>

- in your reports, separate what you measured from what still needs a human to watch or listen

### Quality Bar

<a id="prompt-quality-bar-paragraph-1"></a>

the video isn't done until all of these pass, measured:

<a id="prompt-quality-bar-item-1"></a>

- no more than about 1 second of frozen screen per 30 seconds, and no still stretch longer than about half a second

<a id="prompt-quality-bar-item-2"></a>

- frame one is a finished composition

<a id="prompt-quality-bar-item-3"></a>

- all text meets at least 4.5:1 contrast, and nothing collides with or flies through other text

<a id="prompt-quality-bar-item-4"></a>

- brand colours in 3d renders match the brand values

<a id="prompt-quality-bar-item-5"></a>

- loudness is steady and comfortable for web, with no clipping, and effects never louder than the music

<a id="prompt-quality-bar-item-6"></a>

- a first-time viewer understands it with the sound off

<a id="prompt-quality-bar-item-7"></a>

- a critic would put it next to the references without it looking weaker. a video with no bugs is not the same as a good video

### Deliverables

<a id="prompt-deliverables-item-1"></a>

- the final mp4 in every size requested, at 1080p and 60 frames a second

<a id="prompt-deliverables-item-2"></a>

- a music-only version

<a id="prompt-deliverables-item-3"></a>

- a contact sheet of the final video

<a id="prompt-deliverables-item-4"></a>

- the critic ledger and the final quality bar results

<a id="prompt-deliverables-item-5"></a>

- a short note on anything a human should still check

## Kit non-negotiables

<a id="kit-non-negotiable-1"></a>

1. Truth: never invent testimonials, ratings, completed jobs, diagnoses, savings, warranties or confirmed appointments. Label a concept as “Fictional brand · Concept film · AI-generated imagery” when those labels apply. Client work uses approved facts and real assets.

<a id="kit-non-negotiable-2"></a>

2. Business purpose on mute: by the end a first-time viewer can state what the business does and the single next action. Record this as judgement.

<a id="kit-non-negotiable-3"></a>

3. Independent judging: builders never grade themselves. Every component and full cut goes to a new critic with the round packet; verification rounds add only the previous critic report, never builder claims.

<a id="kit-non-negotiable-4"></a>

4. Deterministic motion: state depends only on timeline time; no free-running requestAnimationFrame, Date.now, unseeded randomness or physics history. Any sought frame reproduces its pixels.

<a id="kit-non-negotiable-5"></a>

5. No bugs is not good: reject basic, empty or slow work even if scripts pass. Measure and judge creatively.
