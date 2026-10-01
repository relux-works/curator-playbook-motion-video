---
name: motion-storyboarder
description: Use only when assigned the motion-video storyboarder role. Draft process role; follows the pinned kit and strict commercial brief.
---

# Motion video storyboarder

Upstream-derived rules: Copyright (c) 2026 echris6, MIT License. The full permission and warranty notice travels in [LICENSE.upstream-mit](LICENSE.upstream-mit). Newly authored process text: License not yet chosen (private draft). The operator decides before publication.

Read [the kit skill](../business-motion-film/SKILL.md), [motion grammar](../business-motion-film/references/motion-grammar.md), then [launch notes](../business-motion-film/references/launch-film-notes.md) at planning. Read [quality bar](../business-motion-film/references/quality-bar.md) before submission. References must already be studied; the five-second setup probe must already have passed.

Write `BRIEF.md` with business, buyer, viewer problem, single CTA, provable facts, approved assets, length, sizes, palette, fonts and forbidden claims. Use a labelled concept when real proof is absent; away mode cannot approve false evidence. Every on-screen number, name and claim gets a facts entry.

One table covers every beat without gaps: time, picture, purpose, exit and carried object. Use 12–15 compositions per 30 seconds, about 1.4–3.5 seconds each, with the lead subject filling 60–85% in feature beats. Keep 1–2 reading targets. Include readable landings, fast exits and overlapping arrivals; the first frame is already finished. Name three signature moments without effect names. Make the single CTA legible at phone size for at least 1.5 seconds; it remains gently alive. Plan the beat grid with the audio designer so every cut lands on a beat.

Vary macro, wide, overhead/plan, UI close-up and type impact. Overhead graphic plans do not permit a top-down large 3D slab. 3D explains physical or spatial information; UI and typography remain HTML/SVG. Send the table and rough frames to a new storyboard critic for chronology, logic, facts, filler, compositions and mute comprehension. Fix ranked findings before any real animation. A storyboard pass is not a rendered-film quality pass.

## Inputs

Film `purpose`, `viewer`, `call_to_action`, `length_seconds`, `sizes`, `brand`, pinned-by-convention `facts_file`/`facts_sha256`, `assets`; completed reference studies or the declared kit fallback; passed five-second setup evidence; previous critic findings on rework.

## Outputs (playbook fields)

Write `storyboard.brief` as `BRIEF.md` with business, buyer, viewer problem, single CTA, provable facts, real assets, length/aspects, palette/type and forbidden claims. Write `table` (time, picture, business job, exit, carried object), `signature_moments` (three), `beat_grid`, `rough_frames`. Pick 3–6 fitting reference mechanisms; cite exact source-video timestamps, or clearly label written-note study. Return a fresh producer outcome with these artifacts.

## Done when

`storyboard.draft → review` requires `fields.present [brief,table,beat_grid,rough_frames]`, lead-owned `signature_moments_declared=true` after checking the three moments, and `outcome.present`. Submission is not acceptance: a new critic records the verdict; `review → accepted` requires fresh `verdict=accepted` and terminal critic records. Fix changes_requested before animation. Report status in one line during long work.

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

### Motion Principles

<a id="prompt-motion-principles-item-1"></a>

1. the thing in the front of the shot becomes the transition. a title, logo or object moves towards the camera while the next scene is already waiting underneath

<a id="prompt-motion-principles-item-2"></a>

2. one object carries the story across shots and keeps its identity, so it reads as one continuous piece

<a id="prompt-motion-principles-item-3"></a>

3. one main movement leads, with smaller ones layered under it, all overlapping. the frame never stops and starts all at once

<a id="prompt-motion-principles-item-4"></a>

4. the speed always changes. things land slowly enough to read, leave fast, and the next thing slows as it arrives. no linear motion

<a id="prompt-motion-principles-item-5"></a>

5. cuts are allowed only when size, direction and subject match on both sides

<a id="prompt-motion-principles-item-6"></a>

6. every action produces a visible result. a scan makes findings, a tap makes a new state, a request makes a confirmation

<a id="prompt-motion-principles-item-7"></a>

7. type is motion too. big words enter from opposite sides, reveal the next scene, and never sit over busy picture without something behind them to stay readable

<a id="prompt-motion-principles-item-8"></a>

8. vary the scale from close, to wide, to overhead, to full-frame type. never repeat the same layout, like a heading over three cards

### Storyboard

<a id="prompt-storyboard-paragraph-1"></a>

write a brief and a storyboard before any animation.

<a id="prompt-storyboard-item-1"></a>

- one table: time, what's on screen, what this moment is for, how it leaves, and which object carries into the next shot

<a id="prompt-storyboard-item-2"></a>

- around 12 to 15 compositions per 30 seconds, each lasting about 1.4 to 3.5 seconds

<a id="prompt-storyboard-item-3"></a>

- the main subject fills most of the frame. no small cards floating in empty space

<a id="prompt-storyboard-item-4"></a>

- frame one is a finished picture, never a word halfway through flying in

<a id="prompt-storyboard-item-5"></a>

- name three signature moments you can describe without using effect names

<a id="prompt-storyboard-item-6"></a>

- the video must make sense with the sound off

<a id="prompt-storyboard-item-7"></a>

- send the storyboard to a fresh critic and fix what it finds before building

### 3D

<a id="prompt-3d-item-1"></a>

- only use 3d where it explains something physical or spatial, like layers, parts, placement or scale

<a id="prompt-3d-item-2"></a>

- light it like a product shoot, with a soft key light from one side and a rim light behind

<a id="prompt-3d-item-3"></a>

- keep the camera between about 35 and 55 degrees. never look straight down on a large surface, and never end tight on a flat one

<a id="prompt-3d-item-4"></a>

- style buildings like a premium architectural model with real materials and a base

<a id="prompt-3d-item-5"></a>

- no floating parts, no gaps where parts meet, no flat black glass, no repeating textures

<a id="prompt-3d-item-6"></a>

- labels are html positioned from the 3d scene every frame, never text inside the 3d

<a id="prompt-3d-item-7"></a>

- measure the rendered background pixel and adjust until it matches the brand colour

<a id="prompt-3d-item-8"></a>

- anything that moves like a real product is measured from real footage frame by frame, and those measurements are the curve

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
