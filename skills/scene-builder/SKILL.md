---
name: motion-scene-builder
description: Use only when assigned the motion-video scene-builder role. Draft process role; follows the pinned kit and strict commercial brief.
---

# Motion video scene-builder

Upstream-derived rules: Copyright (c) 2026 echris6, MIT License. The full permission and warranty notice travels in [LICENSE.upstream-mit](LICENSE.upstream-mit). Newly authored process text: License not yet chosen (private draft). The operator decides before publication.

Read [the kit skill](../business-motion-film/SKILL.md) before building. At motion design read [motion grammar](../business-motion-film/references/motion-grammar.md) and [launch notes](../business-motion-film/references/launch-film-notes.md). At 3D work read [Three.js patterns](../business-motion-film/references/three-js-patterns.md), [component lab](../business-motion-film/templates/component-lab.html) and [projected overlays](../business-motion-film/templates/projected-overlays.js). If a product moves physically, read [product hero realism](../business-motion-film/references/product-hero-realism.md). Read [Gauntlet](../business-motion-film/references/gauntlet.md), [critic prompts](../business-motion-film/references/critic-prompts.md) and [quality bar](../business-motion-film/references/quality-bar.md) before submitting.

Build only after test, studied references, accepted storyboard and locked shared pieces. Own one section and its individual compositions; each composition is a component with a separate HTML lab, stills and a 3–4 second motion proof. Use pinned local GSAP, Three.js, textures and fonts, waiting for every asset and font before capture. Copy the upstream lab into a work artifact and replace its CDN reference with a pinned local file; never edit the vendored template. Animate one seekable root timeline with sub-compositions; map root time to local scene time. No timers, RAF animation, wall clock, history-dependent physics or unseeded randomness. A linear time driver is permitted; visible spatial movement eases and changes speed.

Shared tokens, fonts, models and exact pixel handoff rectangles are read-only inputs. Shared edits go through the lead; stage a .next.js copy, syntax-check it, then replace atomically in the work artifact. A carries-object cut uses the same pose function and exact projected rectangle on both sides, for every size. Render from different seek orders at the same time with the same seed; compare decoded pixels, not encoded file bytes. This test does not prove determinism for untested times or across GPU backends (gap 8).

Use premium architectural maquettes with real materials and base. Soft side key and rear rim; camera pitch 35–55°, minimum distance, no roll or top-down textured slab, pull back rather than finish tight on a plane. No floating joins, ridge gaps, flat black glass, repeating textures or one-frame pops. Typography remains crisp HTML/SVG; project labels and lines from scene anchors every frame with equal spacing, correct pins and correct photo captions. Measure the decoded background and compensate tone mapping until the brand token matches.

For product motion, measure real footage frame by frame for study only. Use angle keys and a monotone cubic with zero endpoint slopes; never guess a generic smoothstep curve. Lock the camera through movement and keep contact still. Preserve screen continuity, lit moving displays, frost over sharp wallpaper and realistic reflections. Use deterministic shutter accumulation for every fast motion; ramp blur and light changes so no brightness step appears. Bind licensed local fonts, size buffers correctly, dispose transient render targets and verify physical realism against dense frames.

Prefer code-built shots. Optional generated stills are key frames first, followed by restrained 4–5 second image-to-video shots with lens, light, exposure, geometry and type-space instructions. No people/text/logos/watermarks when inappropriate. Keep generation model, prompt, seed, job reference and accepted window in the generation ledger, never keys. Any generated support shot is labelled concept; upscale/interpolate honestly and regenerate warped geometry. Paid calls belong to approved tool states, never a builder shell.

The kernel has already run the tool states; its reports stay with the lead. Re-measure with the kit scripts yourself after the lab render; the lead compares the critic's independent numbers with kernel results afterwards in the ledger. The lead routes tool states and a NEW independent critic for every component before it joins the film; you do not invoke kernel tools or post their events. The builder supplies the candidate and facts, never a claim that fixes worked. Do not self-grade. On rework fix the largest meaningful defect, rerender and seek new review; finish not-shipped when limits are exhausted.

## Inputs

Assigned section `section_id`, `compositions`, `shared_input_digest`; accepted storyboard `table`/`beat_grid`; locked shared-kit `tokens`, `fonts`, `models`, `handoff_pixels`, `seed`, `dependency_lock`; facts, references and accepted support assets. Read prior critic findings for fixes but do not send your interpretation to the critic.

## Outputs (playbook fields)

For each scene, produce `composition_id`, `test_page`, `shared_input_digest` and editable component source. The builder returns these values in its outcome. The lead writes them into the scene element before firing `scene.build → rendering`. Kernel component-render produces `proof`, `stills`, `rendered_files`; the lead transcribes those reports. Return section `report` plus a fresh outcome after producing all sources. Do not write `components_ok`, judge acceptance or post tool events. Descendant board writes from a section run are gap 11; report results to the lead, which can route `scene.build → rendering` on your evidence. Do not assume your file scope grants board authority.

## Done when

`scene.build → rendering` requires `fields.present [test_page,shared_input_digest]` and the actual builder outcome. Tool states and fresh critic review precede `scene.review → accepted` (`verdict=accepted`, `children.terminal`). `section.building/fixing → joining` requires your outcome; the lead completes `joining → accepted` only after all scene acceptance, `components_ok=true`, `report` and terminal children. Report status in one line during long work.

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

### Setup

<a id="prompt-setup-item-1"></a>

- build every scene as an html page animated on a single gsap timeline, with three.js for any 3d, all as pinned local files

<a id="prompt-setup-item-2"></a>

- render the timeline to video frame by frame using the renderer in the kit

<a id="prompt-setup-item-3"></a>

- use ffmpeg for frames, contact sheets and audio measurement

<a id="prompt-setup-item-4"></a>

- keep every api key in environment variables. never write a key into any file

<a id="prompt-setup-item-5"></a>

- render a 5 second test first and confirm it works before building the real video

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

## Secret boundary

API keys exist only as environment variables of the trusted provider executor, never any file or agent environment. A renderer executing scene code receives no credentials. This is a role rule plus the proposed sandbox in §6.11.2; see §1 principle 7 and §6.11.
