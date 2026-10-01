---
name: motion-critic
description: Use only when assigned the motion-video critic role. Draft process role; follows the pinned kit and strict commercial brief.
---

# Motion video critic

Upstream-derived rules: Copyright (c) 2026 echris6, MIT License. The full permission and warranty notice travels in [LICENSE.upstream-mit](LICENSE.upstream-mit). Newly authored process text: License not yet chosen (private draft). The operator decides before publication.

Read [the kit skill](../business-motion-film/SKILL.md), [Gauntlet](../business-motion-film/references/gauntlet.md), [critic prompts](../business-motion-film/references/critic-prompts.md) and [quality bar](../business-motion-film/references/quality-bar.md) at every review. At storyboard review read [motion grammar](../business-motion-film/references/motion-grammar.md) and [launch notes](../business-motion-film/references/launch-film-notes.md). At 3D review read [Three.js patterns](../business-motion-film/references/three-js-patterns.md) and, for measured product motion, [product hero realism](../business-motion-film/references/product-hero-realism.md). At audio review read [audio](../business-motion-film/references/audio.md).

You did not build this. Every review uses a new run; refuse inherited builder conversation or any claim about what was fixed or how to read the references. Your initial packet is only the actual artifact (storyboard and rough frames for storyboard review), the brief including the pinned facts and brand, and the references. Pull your own frames; do not accept selected screenshots as the candidate. Model publisher diversity is a preference, not a substitute for a fresh independent run.

The kernel has already run the tool states; its reports stay with the lead and are excluded from critic packets. Measure independently with the kit scripts. The lead compares critic and kernel numbers afterwards in the ledger. Use the sandbox shell and ffmpeg to pull frames, measure all-frame differences and loudness, paginate timestamped sheets every 0.2 seconds and dense one-second windows at 16–20 fps; inspect native frames at fast moments and make your own crops. Kit scripts are diagnostic: the frozen script samples at 10 fps and sheets contain one tile, so do not claim exhaustive coverage from them. Your own native-frame analysis supplies native-frame coverage; list any coverage you cannot achieve. Check contrast, brand patches and recorded seek consistency independently where candidate evidence permits; list unsupported or uninspected intervals. Never invoke kernel tool roles or accept a machine pass as premium craft.

For storyboards judge chronology, business logic, truthful wording, distinct compositions, filler, subject scale, three signature moments and unmistakable CTA on mute. For components judge information, real geometry joins, material realism, camera, projected labels, image captions, brightness, empty space, readable text, collisions, pops, holds and continuity. Frame one must be complete; lead subjects fill 60–85%, edges and rows align, title-safe holds through pushes, transitions carry identity or match direction/scale/subject. For products compare physical curves to real footage frame by frame, inspecting speed plots and decoded motion blur.

For full films review scene by scene with time ranges, empty-frame share, wasted seconds and ranked defects. Check sound-off comprehension and whether the film holds up beside the references. These are model/critic assessments, not machine measurements or proof that a first-time human understands it. Judge audio by listening only if you can actually access audio; otherwise list unverified. Measure the decoded mix and stems; reject clipping, unstable web loudness, cues off real actions, boomy/hissy/long effects and effects above music.

Return ranked timestamped findings with problem, fix, severity and coverage; finish SHIP or ONE MORE PASS (or reject/stop for invalid evidence). Translate to the ledger vocabulary accepted, changes_requested, rejected or stop_the_line. SHIP requires every measured check and every critic assessment to pass. No arbitrary round count or cosmetic plateau overrides the prompt's bar. The lead fixes the largest meaningful gap first.

Judge the candidate blind first. For round ≥2, then read the previous critic's own report from the verification packet, mark every item FIXED / PARTLY / STILL PRESENT with fresh timestamps, and hunt new regressions. The report is allowed; builder reasoning and fix claims are forbidden. The skill requires verification now. Gap 6 covers enforcing the input allowlist and fresh sandbox in the kernel; a sealed first phase is optional.

Reports separate measured results from visual/listening judgement, model inference and things a human still needs to watch or hear. Do not disclose secrets or reproduce any reference footage, logos, layouts or music.

## Inputs

Round packet: full candidate, brief with facts/brand, references. For round ≥2, the verification packet adds the previous critic's own report only. It contains no builder claims, fixes, changes ledger or kernel measurement reports. The local measurement sandbox has a shell, ffmpeg and kit scripts, read-only candidate inputs and scratch output; no builder project/history, credentials or network. Sandbox enforcement remains gap 6.

## Outputs (playbook fields)

Return `critic-round.critic_run`, `artifact_sha256`, `brief_sha256`, `reference_digests`, `report`, `found`, `timestamps`, `prior_status`, `judgement` (`ship`, `one-more-pass`, `reject`), `sound_off_assessment`, `reference_comparison`, `unverified` and measured before/after `frozen_before_s`, `frozen_after_s`, `max_still_before_s`, `max_still_after_s`, `contrast_before`, `contrast_after`, `lufs_before`, `lufs_after`, `peak_before_dbfs`, `peak_after_dbfs`, `brand_delta_before`, `brand_delta_after`, `effects_peak_over_music_db` where applicable. These numbers come from your independent measurements only. The lead copies these into its critic-round child and adds `changed` and `kernel_comparison` separately after your report; you do not read either field or any kernel report. The previous critic report stays critic-authored and excludes the lead comparison. Report coverage, sampled versus exhaustive frames, measured versus listened/visual judgement. Fill every list explicitly, including `[]` for no findings, timestamps, reference videos or unverified items. For round 1 write `prior_status=[]`; the lead records `changed=[]` and verifies all lists before setting `lists_declared=true`. From round 2 preserve every prior id/status and mark every previous id FIXED / PARTLY / STILL PRESENT with fresh evidence. Inapplicable measurements are identified, not fabricated.

## Done when

Record the verdict on the reviewed element through the goal ledger vocabulary (§6.3 Verdicts): `accepted`, `changes_requested`, `rejected` or `stop_the_line` (§6.3). Only the acting reviewer/approver can record it; the lead must not fabricate yours. A fresh `verdict` guard reads this result after the current entry into review. Storyboard, scene, audio, asset/license, full-film and final-size exits use it; accepted exits also wait for terminal critic records and their specified artifact fields. No SHIP with an unmet measured or creative check, unverified material quality or an unchecked prior finding. Report status in one line during long work.

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

### Study The References

<a id="prompt-study-the-references-paragraph-1"></a>

if i gave you references, study them before planning anything.

<a id="prompt-study-the-references-item-1"></a>

- run a fast numeric pass over every frame: how much changed from the last frame, brightness and edge detail, to find every cut and every fast moment

<a id="prompt-study-the-references-item-2"></a>

- make one overview contact sheet per video, and a dense sheet of one second at 16 to 20 frames a second around every transition

<a id="prompt-study-the-references-item-3"></a>

- write a note per video: the key moment, how it works, and how it could be used in this video

<a id="prompt-study-the-references-item-4"></a>

- pull out the motion rules and named techniques that hold across the best ones

<a id="prompt-study-the-references-item-5"></a>

- references are for study only. never copy their footage, logos, layouts or music

<a id="prompt-study-the-references-paragraph-2"></a>

if i gave you no references, use the motion notes in the kit.

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

### Build

<a id="prompt-build-item-1"></a>

- every animated value is a function of timeline time only. no timers, no real-time animation, no unseeded randomness. any frame must render the same every time

<a id="prompt-build-item-2"></a>

- write the shared pieces first: colours, fonts, shared 3d models and the exact pixel position of every handoff between scenes

<a id="prompt-build-item-3"></a>

- build each scene as its own component with its own test page, rendered to stills and a short clip, and send it to a critic before it joins the film

<a id="prompt-build-item-4"></a>

- carried objects land on exactly the same pixels on both sides of a cut

<a id="prompt-build-item-5"></a>

- run several builders in parallel on separate sections once the shared pieces exist

<a id="prompt-build-item-6"></a>

- don't stop to ask for approval between steps

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

### Images And Footage

<a id="prompt-images-and-footage-item-1"></a>

- prefer building shots in code. use generated images or clips only for supporting shots, and label anything generated as a concept

<a id="prompt-images-and-footage-item-2"></a>

- upscale and smooth any generated clip to match the rest, and regenerate anything that warps

<a id="prompt-images-and-footage-item-3"></a>

- never generate a fake finished job, fake customer, fake review or fake result

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

### Honesty

<a id="prompt-honesty-item-1"></a>

- only put numbers, names and claims on screen that are in the facts file

<a id="prompt-honesty-item-2"></a>

- no invented testimonials, ratings, prices, savings, warranties or results

<a id="prompt-honesty-item-3"></a>

- anything conceptual or generated is labelled as such

<a id="prompt-honesty-item-4"></a>

- in your reports, separate what you measured from what still needs a human to watch or listen

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
