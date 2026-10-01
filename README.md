**DRAFT — This is a draft playbook package. It depends on curator-playbook DRAFT v4.8 (commit `7137dd2`). Nothing runs until PC1. Tool states and the proposed evidence, file and sandbox features also need PC3. It is not normative or runnable.**

# curator-playbook-motion-video

Original skill (prompt and kit) by @everestchris6 (GitHub: echris6), https://github.com/echris6/motion-video-kit, MIT License. This package adapts it to the process-configuration model; the vendored kit is unchanged.

## What the package is

A draft process for an autonomous, code-built commercial. A production lead studies references, plans a storyboard, locks shared pieces, fans out section builders, and iterates actual renders with independent critics. Machine steps have tool owners. The brief owner supplies the inputs, delegates the named intake advance and bounded spending before departure, and receives the deliverables while away.

This is a second video-production generality check beside the system's music-video example. It adds code determinism, exact scene seams, a strict measured quality bar and restricted fresh-critic input. It creates no film and publishes nothing. Read [precedence](docs/precedence.md) for source conflicts and [traceability](docs/traceability.md) for every prompt rule.

## Files

| File | Content |
| --- | --- |
| [motion-video.playbook.json](motion-video.playbook.json) | schema-version-1 template, current mechanics and explicitly ignored PC3 proposals |
| [examples/project.Playbook.json](examples/project.Playbook.json) | typed concept brief, away-mode policy, capability needs and process WIP limits |
| [examples/facts.md](examples/facts.md) | sole source for example on-screen words; exact digest in the example |
| [examples/task-board.config.json](examples/task-board.config.json) | draft named check-set definitions; provider commands are not implemented |
| [skills/orchestrator](skills/orchestrator/SKILL.md) | production lead, carrying [data/playbook.json](skills/orchestrator/data/playbook.json), identical to the root template as §8.1 requires |
| [reference analyst](skills/reference-analyst/SKILL.md), [storyboarder](skills/storyboarder/SKILL.md), [scene builder](skills/scene-builder/SKILL.md), [audio designer](skills/audio-designer/SKILL.md), [critic](skills/critic/SKILL.md) | full applicable rules for each agent role |
| [skills/business-motion-film](skills/business-motion-film/SKILL.md) | unchanged upstream skill, references, scripts and templates, plus upstream LICENSE |
| [tools/motion-tools](tools/motion-tools/SKILL.md) | provider contract only; outside the collection under §8.5 |
| `skills/{orchestrator,reference-analyst,storyboarder,scene-builder,audio-designer,critic}/LICENSE.upstream-mit`; [provider notice](tools/motion-tools/LICENSE.upstream-mit) | seven verbatim MIT permission/warranty notices; one inside each independently installed role/provider directory |
| [quality checks](docs/quality-checks.md), [provider contracts](docs/provider-contracts.md), [precedence](docs/precedence.md), [traceability](docs/traceability.md) | checks, evidence limits, source decisions and complete rule mapping |
| [upstream/PROMPT.md](upstream/PROMPT.md), [upstream/SOURCE.md](upstream/SOURCE.md), [upstream/LICENSE](upstream/LICENSE), [NOTICE](NOTICE) | supplied prompt/header, source pin, per-file SHA-256 table and MIT notice |

### Tools used in this package

The target is HTML/GSAP, optional Three.js and frame-by-frame video rendering. No Apple or unrelated platform build is needed for this data package.

| Tool | Use and exact entry point | Outputs |
| --- | --- | --- |
| check-jsonschema | `check-jsonschema --check-metaschema "$PLAYBOOK_SCHEMA"`; `check-jsonschema --schemafile "$PLAYBOOK_SCHEMA" motion-video.playbook.json examples/project.Playbook.json` | terminal; captured validation logs in `.temp/` |
| ripgrep | `rg --files -uu -g '!.git/**' -g '!.temp/**'`; `rg -n pattern README.md docs skills` | file and rule inventory in terminal; readiness logs in `.temp/` |
| Python 3 | `python3 -m json.tool motion-video.playbook.json`; upstream diagnostic script examples below | parsed JSON in terminal; readiness/validation evidence in `.temp/` |
| ffmpeg / ffprobe (future provider) | kit entry points below; actual provider invocations must use Curator commands and the kernel executor | work artifact frames, sheets, decoded audio and reports |
| HTML/GSAP, Three.js and a pinned renderer (future provider) | copy `templates/component-lab.html` to the film work artifact, bind local dependencies, use its documented snapshot/render entry points with a pinned renderer | component stills, motion proofs and final MP4s in invocation artifacts |

Set `PLAYBOOK_SCHEMA` to the pinned system schema. No network is needed for package validation. Local validation evidence belongs in `.temp/`; no scratch script is a shipped entry point. The renderer, contrast/colour/difference/determinism adapters and audited Curator providers remain unimplemented.

The upstream scripts are unchanged diagnostics. Exact examples, with inputs supplied by the future provider:

```sh
bash skills/business-motion-film/scripts/contact-sheet.sh film.mp4 sheet.jpg 0.2 6 5 0 6
bash skills/business-motion-film/scripts/frozen-time.sh film.mp4 0.35
bash skills/business-motion-film/scripts/loudness.sh film.mp4
bash skills/business-motion-film/scripts/soften-sfx.sh in.mp3 out.mp3 150 6500
python3 skills/business-motion-film/scripts/sfx-candidates.py candidate.wav
python3 skills/business-motion-film/scripts/solve-sfx-gains.py music_only.mp4 events.json 3.5 4
```

Sheets must be paginated; the frozen script samples at 10 fps. The future provider must decode native frames for exhaustive checks. The upstream offline mixer is a fixed 40-second worked example; adapt only a work copy for the new film. Never mistake its defaults for the task's stricter mix rules. These media commands were read, not executed in this package task.

## Install

One Skillfile collection entry installs all role skills and the kit (§8.2). This full example is a future publication recipe. The repository source and tag below are proposed, not a published or audited release. The operator must choose the package license and provider identities first. The recipe does not perform installation or request network access.

```json
{
  "schema_version": 2,
  "sources": {
    "motion-video": {
      "git": "https://github.com/relux-works/curator-playbook-motion-video",
      "tag": "v0.1.0-draft"
    }
  },
  "skills": [
    { "from": "motion-video", "directory": "skills", "include": ["*"] }
  ]
}
```

Under the §8.2 stopgap the kit skill is also installed as an ordinary project skill with its unchanged generic description. The Skillfile can add `"exclude": ["business-motion-film"]` once role profiles carry the kit as a dependency (gap 9).

Role `data/role.json` metadata is deferred to its PC2 schema (§8.1); current capability/needs declarations live in the template, and each skill contains Inputs, Outputs and Done when. The template must resolve from the project scope and committed lock. Role profiles carry only their assigned role plus the kit dependency. Tools sit outside `skills/` and must arrive as audited, runtime-only dependencies narrowed to their exported commands; [provider contracts](docs/provider-contracts.md) describe the missing manifests. No hand-copied skill or shell shim grants tool admission.

The example's delegation policy is permission to grant, not a grant. Before leaving, the real brief owner confirms the process, a grant for the single intake advance, and a scoped, expiring spending grant with a 5 USD per-request ceiling and a 50 USD rolling-day budget. `self_approval` covers only spending estimates the lead drafted; it never licenses self-review. No mid-run human taste gate is added. Missing authority or exhausted budget ends not-shipped if cleared local alternatives cannot satisfy the brief. The example principal pattern must resolve against the real private roster. The example cannot run on PC1 as shipped because policy.signatures requires approvals, spending and delegations whose signable forms arrive in CM2 (§4.2). In particular, the required away-mode grant is impossible on PC1. PC1's interim trust is only a guardrail.

For a PC1 demo variant, apply this short diff to the example; no second project file is supplied. This removes only the signature-policy blocker. The tool states still need PC3 and real providers, so it does not make this motion-video example runnable on PC1 alone. The owner must still confirm the process and actual scoped grants before departure; use a single-host board for a budgeted grant before CM2.

```diff
-    "signatures": {
-      "require_for": [
-        "approvals",
-        "spending",
-        "delegations"
-      ],
-      "min_assurance": "hardware-bound",
-      "user_verified": "required"
-    },
```


Machine capacity belongs in private `runtimes.toml` (§2.3). The ignored setup checklist in the example records four parallel runs, one local check set, one render resource and one analysis resource without naming machines. The public WIP values count elements and cannot provide a shared machine lease.

## How the process maps

| In the skill | In the playbook | Spec § |
| --- | --- | --- |
| Five-second test before building | `film.test-setup → test → studying`, test-render tool | §6.11 |
| Study supplied references before planning | `create reference per style_references`; frame-difference, sheets, analyst, terminal join | §5.1, §6.1, §6.3 |
| Brief and storyboard before animation | typed film inputs; storyboard draft and critic-owned review | §5.2, §6.3 |
| Tokens, models and exact handoff pixels first | `shared-kit`, locked before section fan-out | §5.1, §6.1 |
| Several builders on separate sections | `create section per sections; scene per compositions`; builder WIP; lab proof and component critic | §6.1, §6.3, §6.8 |
| Selective 3D | vision and tool-use capability needs plus full 3D builder skill rules; no independent 3D owner is needed | §4.1, §9 |
| Builder never judges its work; new blind critic | separate reviewer role and review states; context/fresh-run rules are gaps | §4.3, §6.1, §6.16 |
| Measured quality and creative ship bar | tool pipeline plus critic verdict; documented proposed check sets | §6.11, §6.12; gap 7 |
| Fix, render, new critic, verify prior items | bounded rework, fresh critic, previous critic report in verification packets, typed item statuses; no builder claims | §6.2, §7.3, §6.16; gap 6 |
| Facts are the sole source | facts path/hash and complete role rules; pinned content proposal | §5.2, §5.5 |
| Generated support / licensed music costs money | spending risk, approvals, delegated ceiling and pre-run grant budget | §4.2, §6.4, §6.11.1 |
| Repeatable frames | determinism tool plus pure-time and seeded-randomness role rules | §6.11; gap 8 |
| Final MP4 in each size, music-only and evidence | `create deliverable per sizes`, final render, music-only, sheets, per-size metrics/contrast/colour/determinism, audit and critic; parent return to source rework | §5.1, §6.3, §6.11 |

The order is partly structural and partly checked by the lead. Terminal joins wait for completion; accepted verdicts gate individual artifacts. They do not prove that every child succeeded (gap 10).

| # | Required order | What enforces it |
| --- | --- | --- |
| 1 | Five-second test before real build | Structural: tool.passed leaves `film.test` for studying; production fan-out is later. |
| 2 | Reference study before planning | Supplied videos: terminal join plus lead `references_ok` and `references_declared_none=false`. No videos: explicit lead-owned `studying → no-references → planning`, `references_declared_none=true` and `references_ok=true`; no empty join. |
| 3 | Brief/storyboard before animation | Structural: storyboard draft requires brief/table/beat grid/rough frames plus lead-declared signature moments; build fan-out follows planning. |
| 4 | Storyboard critic before build | Individual fresh verdict guard is structural; film join also relies on lead `storyboard_ok`. |
| 5 | Shared pieces before parallel builders | Structural terminal join; lead `shared_ok` confirms locked success and complete inputs. |
| 6 | Component critic pass before film join | Individual scene verdict is structural; section/film joins also rely on lead `components_ok`. |
| 7 | Full-render loop until ship | Structural measured/critic loop, then the same bar per final size; finite default ends not-shipped. Lead `exports_ok` confirms all current size evidence. |

A final-size failure enters `deliverable.rework`; `film.packaging → rework` detects that child with `children.any-in`. The lead invalidates all sizes, repairs/reviews sources, obtains a fresh full-film verdict, then requeues the existing size elements and repeats every check. The first accepted full film uses `export-setup` for a single size fan-out; lead `exports_created` distinguishes later passes. Source-digest freshness still needs gaps 1 and 7.

## What the model makes better

- The declared test prevents real production before the rendering path works.
- Reference study, storyboard review, shared inputs, component reviews and final reviews are visible board states that can be resumed.
- Parallel sections meet at explicit pixel seams, then a tool checks them after the join.
- Tool owners keep machine work outside the builder's environment. The future sandbox must keep renderer code away from secrets.
- Spending is constrained by a real delegation and its budget. Silence is never approval.
- Render and critic rounds retain separate measured and judged results. A clean render cannot pass by a builder's taste alone.

## Gaps this check found

Items 1–5 are already proposed in DRAFT v4.8 for PC3. Items 6–12 are new proposals or unresolved distribution requirements; gaps 7–8 are partly covered by §5.5. Every `x-` block is ignored by the kernel. Schema validation does not implement any of these features.

1. **Content-bound facts and artifacts** (Already proposed for PC3; §5.5). Adopt file fields, pinned inputs, part sets, licence provenance, inputs.fresh and supersession. Current string paths and a declared hash are role conventions; they do not bind file contents or invalidate descendants.

2. **Typed tool results and receipts** (Already proposed for PC3; §6.11.1). Also found by `examples/music-video` gaps 1–2. Adopt outputs, spends and receipts. The kernel writes measurements, reconciles charges and preserves unknown outcomes. Until §6.11.1 outputs exist, automatic tool-to-tool handoff uses the provider convention in [local contracts](tools/motion-tools/references/contracts.md): a provider-configured artifact directory, element id, entry-keyed stage manifests and a digest-bound active candidate. It does not depend on lead transcription between automatic states. The lead stages confirmed inputs before a chain and transcribes bounded stdout/report paths into typed ledger fields after the chain reaches an agent-owned state. Reads, candidate locations and printed keys are specified per command. This is a provider contract, not a kernel outputs feature; trusted manifest storage and freshness validation are provider readiness requirements.

3. **Render resources, readiness and secret isolation** (Already proposed for PC3; §6.11.2). Adopt pinned trees, resource leases, resumable progress, final tiers, probe and executes: element-content sandboxes. Per-state WIP limits are process limits, not a shared machine semaphore. Scene rendering receives no credentials.

4. **Numeric quality parameters and plan budgets** (Already proposed for PC3; §6.14 (extends §7.3)). Adopt number/string params in comparison values and tool settings. The x-pc3.quality_params block records the intended thresholds, including 0.5 s, 4.5:1 and signed loudness. It is ignored, not an executable parameter set. frame_diff_threshold=0.35 is tied to its explicit 10 fps, 320-wide YAVG diagnostic basis; the native 60 fps threshold is unset until calibrated and declared by the provider. Spending grants add money budgets; credits and plan-digest budgets remain PC3.

5. **Typed critic findings and verified capabilities** (Already proposed for PC3; §6.16 and §9). Adopt time-coded findings, unverified lists, vision/video-input/audio-input registry rows and per-section writes. Also found by `examples/music-video` gaps 5–6. `code-generation` is not a §6.16 registry proposal; the package drops it from require and keeps `tool-use` plus the builder skill rules. Existing list fields preserve reports without a structured finding type. Capability strings validate today, but a registry must actually support them.

6. **Fresh critics with an enforced input allowlist** (New; §6.1 and §6.16). Propose a new run per candidate digest, excluding all producing runs and inherited production context. The round packet is candidate, brief with facts, and references. Kernel measurement reports are excluded. The critic measures alone; the lead compares its numbers with kernel numbers afterwards in critic-round.kernel_comparison and the film ledger, including basis/coverage and discrepancies. The previous critic report remains critic-authored and excludes the lead comparison. For round ≥2 the verification packet adds only the previous critic's own report. The skill requires blind judgement followed by FIXED / PARTLY / STILL PRESENT verification now; the sources do not conflict. The missing kernel feature is enforcement of this allowlist and provenance. Blind helpers only hide peer answers today. The current not_same_publisher_as=scene-builder preference covers component evidence only; it is vacuous for storyboard, audio, asset and licence producers. Extend selection to the actual producing run at each review state. No publisher preference proves independence. A sealed first phase is an optional stronger proposal. Give the critic a measurement sandbox with local shell, ffmpeg and kit scripts, candidate inputs and scratch outputs only; no builder files, credentials or network.

7. **Check sets for artifact acceptance** (New extension; §6.12; partly covered by §5.5 (approvals bind content; supersession is read-only)). What is new is check-set evidence for artifacts without a Change Request. Proposed artifact.checks-passed gate with evidence bound to candidate content digest, size, fps, final tier, provider and pinned inputs; no inline pass when evidence is missing. Generic tool states gate this draft. The documented named sets are future definitions, not delivery-module guards: delivery.checks-passed passes an element without a Change Request and would be false assurance.

8. **Evidence scope, truth audit and immutable round history** (New extension; §5.2 and §6.16; partly covered by §5.5 (approvals bind content; supersession is read-only)). What is new is the facts-to-screen audit and the remaining evidence-scope guarantees. Propose append-only round records linked to immutable candidate digests and evidence coverage. Require a machine facts-source audit for every on-screen name/number/claim, and distinguish sampled determinism from a universal pure-time guarantee. Current typed fields and separate critic owners do not enforce an immutable ledger, exact claims provenance, global no-self-review outside delivery, or proof over every possible frame/backend. Keep these as complete skill rules until evidence guards exist.

9. **Installed kit assets and provider distribution** (New residual; §8.1–§8.5, especially §8.3 item 2; §17.3 item 16). `dependencies.skills` with `directory` already covers dependency selection; profiles as package content are an open question. Neither defines an installed asset path handle. Propose content-addressed dependency assets in role profiles so kit links resolve across independently installed skills. Package links work in the source tree; mandatory precedence rulings are now inline in every role, and the full MIT notice is local. The provider carries its contract table and quality guidance under tools/motion-tools/references/; its installed SKILL.md has only local links. Remaining sibling kit links in role skills are study links that require the profile dependency and the proposed asset addressing, not guaranteed installed paths. HyperFrames is the kit's intended reference renderer, named by its README and lab template; its unpinned `npx hyperframes` example is not a provider. Pin and vendor the renderer and dependencies in a future audited provider, with runtime-only manifest command narrowing. The kit stays byte-identical. Missing providers are a readiness blocker.

10. **Success-only join** (New; §6.1 rule 2, §6.3 and §10 join coverage). `children.terminal` cannot tell accepted from not-shipped. `children.in` must cover every terminal state, so it cannot be narrowed to success alone. Propose a guard that passes only when every required child of declared types is in a named success state, and permits a declared empty fan-out. Does children.terminal pass with no children? v4.8 §6.3 does not define that case; it remains an unresolved kernel question. The example avoids it: references_declared_none=true takes the explicit lead-owned studying → no-references → planning path with references_ok=true and no children.terminal guard. The lead verifies empty style_references and no reference children, studies written kit notes and records the narrower basis before setting references_ok. The supplied-video path requires references_declared_none=false and the usual terminal join. These boolean fields are lead assertions, not kernel list-cardinality proof. Current other joins use lead-owned success flags. `children.any-in` failure routes expose not-shipped/stopped production children to the kernel but do not prove all-success. Historical render-round.failed records describe recoverable invocation failures and do not trigger these production joins. Does `fields.present` pass on an empty list? v4.8 does not define that case. The package no longer depends on its answer: every list is excluded from fields.present, and lead-owned boolean declarations distinguish explicit empty values from missing work and check required non-empty lists. The lead fills lists even when empty; these remain assertions, not kernel list-cardinality proof. The kernel resets four lead-owned flags, in six states, through `clear_on_exit`: `components_ok` on `film.rework`, `film.seams` and `section.joining`, `signature_moments_declared` on `storyboard.draft`, `licenses_declared` on `audio-piece.design` and `final_sheets_declared` on `deliverable.queued`. The lead still resets every other declaration when its inputs change.

11. **A run acting on descendant elements in its write scope** (New; §4.2, §6.3 own_element and §6.16 write scopes). One builder run per section produces the scene sources. v4.8 gives a run its own element's exits and proposes file write scopes; it does not grant descendant board authority. Propose a recorded subtree scope with explicit permitted descendant types, fields and agent-owned exits; tool execution remains kernel-only. Until adopted, the lead routes scene exits and records builder outcomes. The section file scope alone must not be treated as a board lease.

12. **Agent role unavailable while the owner is away** (New; §4.2 rule 1, §6.2, §6.9 and §9). A critic with on_unmet=block may fail selection before a run starts; builder/analyst/designer selection can also stall. Every critic-owned review/verify state now has on.after=$review_deadline (default PT3H, matching the render timeout), ending not-shipped with resolution unverified without inventing a verdict. Kernel tick must remain live. A stalled critic and a slow critic are the same case here: both hit this wall-time deadline. This bounds review waits, but other agent-owned work states still have no generic availability watchdog. Propose an agent-unavailable event and an entry/selection deadline for every agent-owned state, with a declared failure route and propagation to waiting parents. Session budgets in proposed §6.14 cover running sessions, not refused selection.

## Playbook check

The package exercises these §11 vectors:

| Vector | Case |
| --- | --- |
| Custom typed fields | brief, facts digest, pixel handoffs, audio plans and before/after metrics |
| Human owners | brief owner owns intake, delegates its advance before departure, approves bounded spending and receives files; no mid-run taste state |
| Tool owners | setup render, analysis, audio and final export machinery |
| Timers | automatic kernel deadline fallback after each tool binding timeout and each critic review/verify deadline |
| Parallel branches and join | references per video; builders per section; exports per size; terminal joins |
| Loop limits with escalation | finite rework returns end not-shipped while the owner is away |
| Resolutions and reopen | failure reasons; accepted scene/audio reopening for defects found in context |
| Routes on field values | optional image/clip route; orchestrator success fields after child outcome inspection |
| Limits on work in progress | section.building count and render-state element limits |

No recurrence, external event, cross-process handoff, quorum or privacy vector is claimed. Seams between parallel siblings are the §6.16 pattern, not a new kernel feature.

New vectors: fresh reviewer provenance with restricted context; content-bound measured artifact acceptance; deterministic seek replay; facts-only screen content; away-mode autonomous quality loops that fail honestly rather than forcing ship. They expose gaps instead of pretending the kernel already enforces them.

## License

The upstream kit and text copied or closely adapted from it remain MIT, with “Copyright (c) 2026 echris6” preserved. [NOTICE](NOTICE), [upstream/LICENSE](upstream/LICENSE) and [the vendored LICENSE](skills/business-motion-film/LICENSE) travel with those parts.

The prompt's licence is not stated upstream; it is reproduced with attribution and treated as MIT for caution. That treatment is not proof of permission from its author. Each adapted role and provider directory carries a verbatim `LICENSE.upstream-mit`; the notice travels even when one skill is installed alone.

Our own new text (playbook JSON, original process instructions and docs): **License: not yet chosen (private draft). The operator decides before publication.** Upstream-derived passages within role skills retain MIT. There is no root LICENSE for our parts.
