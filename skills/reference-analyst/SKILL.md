---
name: motion-reference-analyst
description: Use only when assigned the motion-video reference-analyst role. Draft process role; follows the pinned kit and strict commercial brief.
---

# Motion video reference-analyst

Upstream-derived rules: Copyright (c) 2026 echris6, MIT License. The full permission and warranty notice travels in [LICENSE.upstream-mit](LICENSE.upstream-mit). Newly authored process text: License not yet chosen (private draft). The operator decides before publication.

Study before planning. Use only supplied reference videos, or the kit's [motion grammar](../business-motion-film/references/motion-grammar.md) and [launch notes](../business-motion-film/references/launch-film-notes.md) when none are supplied. Read [the kit skill](../business-motion-film/SKILL.md) first.

Kernel reports for your reference are in your packet; you may use them. You do not invoke kernel tool roles. Measure independently with the kit scripts. Use a local shell and ffmpeg for independent diagnostics. The numeric pass covers every native frame: change, brightness and edge detail, cuts and fast moments. Create a paginated overview per video and a one-second 16–20 fps dense window around every transition. Write timestamped notes for each video: key moment, mechanism, transfer to this brief. Extract shared motion rules and name techniques. Never copy footage, logos, layout or music. Notes based only on written kit analysis must say so. Numeric heuristics locate moments; visual study confirms them.

The kit's [contact-sheet script](../business-motion-film/scripts/contact-sheet.sh) produces one tile only; make enough pages to cover the entire video. Do not call a sampled sheet an exhaustive review.

## Inputs

`reference.reference_id`, `video`, the film brief/facts/brand, supplied reference file, kernel frame-difference and contact-sheet evidence. With no supplied videos, the lead records the kit-note fallback before planning; do not invent a reference child or numeric video pass.

## Outputs (playbook fields)

You write `reference.study` and the fresh analyst outcome: key moments, exact timestamps for actual supplied video, mechanisms and application to the brief; shared rules and named techniques. Pick 3–6 fitting moments from launch notes; say which were studied from written notes only. Include your independent diagnostics, coverage and evidence paths in `study`. The lead alone writes `reference.numeric_report` and `reference.sheets` from kernel frame-difference/contact-sheet outputs after the tool chain; the analyst does not write those two fields.

## Done when

`reference.studying → studied` reads `fields.present [study,numeric_report]`, lead-owned `sheets_declared=true` and `outcome.present`. No numeric/visual observation is complete without its source and coverage. Report status in one line during long work.

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

### Honesty

<a id="prompt-honesty-item-1"></a>

- only put numbers, names and claims on screen that are in the facts file

<a id="prompt-honesty-item-2"></a>

- no invented testimonials, ratings, prices, savings, warranties or results

<a id="prompt-honesty-item-3"></a>

- anything conceptual or generated is labelled as such

<a id="prompt-honesty-item-4"></a>

- in your reports, separate what you measured from what still needs a human to watch or listen
