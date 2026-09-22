# Tool-aware pet creation

Read this when creating or repairing pet artwork. Use the installed `hatch-pet` skill for format, job preparation, generation, QA, and packaging; use `imagegen` for visual generation. Locate those skills through the current catalog. If unavailable, explain the missing dependency and provide the prompt/package work that can be completed without it. Do not invent their scripts or API parameters.

For optional Ruflo support, read [tool-routing.md](tool-routing.md). A memory search can recover a useful lesson; it cannot approve an image or replace validation.

## Resolve the visual contract before generation

Record the name, body construction, palette, exact requested markings, props, animation semantics, and reference roles. Keep tool names, orchestration instructions, and memory records out of image prompts.

For ruPet the stable identity is a rounded charcoal robot, cyan face panels, purple accents, and a small lowercase **ru** chest emblem. The explicit emblem request wins over a generic “no text” default. Normalize that default to “no unrequested text, captions, frame labels, or guide marks; preserve the requested ru emblem.” Apply the same contract to normal and retry prompts. Do not infer new logos from a project name or memory result.

Keep the cyan eye glow inside the face panel so it reads brightly without a detached halo. Accept genuine transparency when the image tool supplies it and the deterministic pipeline validates it; do not reject a usable image solely because it returned alpha instead of the requested chroma background.

## Use tools at useful checkpoints

1. **Prepare:** inspect existing files; optionally search `rupet` memory once for relevant validated lessons. Prepare the on-disk manifest with hatch-pet. Record any adopted lesson as an assumption to verify.
2. **Generate:** the parent dispatches only jobs whose dependencies pass. Use one bounded visual job per fresh worker, up to three concurrently when supported. If the host cannot release worker slots, finish pending work or execute the next ordinary generation job locally; never reuse a labeled worker as a blind reviewer.
3. **Check incrementally:** copy the selected source, run the row checks, and retain its QA result before marking that job complete. A worker's confidence or a Ruflo task status is not the acceptance gate.
4. **Repair:** classify the failure and change its root condition. Use deterministic fixes for extraction problems; generate again for wrong visual content. After two recurrences of the same cause, change the pose specification or mechanics instead of repeating the same prompt.
5. **Assemble and review:** retain the hatch-pet gates, including the four cardinals, coherent gaze rows, three isolated blind reviews, final semantic review, transparency checks, and package validation. Inspect metrics alongside visible evidence.
6. **Deliver and retain lessons:** install only when installation is in the requested scope, and only after the package is validated; otherwise deliver the requested artwork or package. When installing, verify copied artifacts match the validated package. Record bounded lessons with evidence. Report “installed” separately from “selected in the app.” Publishing and scheduling require their own user scope.

Use Ruflo task tracking only if the run must be coordinated across sessions. Store references to artifacts and brief lessons, not duplicate manifests or image payloads. On resume, reconcile the actual files and validators before trusting cached status.

## Pose prompts that reduce repeated repairs

### Directional movement

Specify a visible rhythm instead of merely saying “running.” For a biped, describe eight poses as two cycles of extended stride, narrow passing/recovery, opposing stride, and passing/recovery. Identify near/far limbs through consistent overlap, not new colored labels. Keep face direction correct, preserve scale and feet baseline except for intentional bounce, and exclude trails, shadows, or effects.

At pet size, judge whether extension and recovery visibly alternate and the loop reads as movement. A stylized cycle need not be a biomechanical simulation. A repeated static stride still fails.

Do not mirror a row when it reverses the ru emblem, other readable marks, asymmetric props, or meaningful handedness. Preserve temporal order if mirroring is approved for another character.

### Gaze

Anchor the torso and feet. Turn and pitch the separate head; shift the cyan face features on their display surface. Establish unmistakable up, right, down, and left anchors before intermediate angles.

For each diagonal, state both cues: face/eye center shifted to the intended side **and** head pitch/chin/crown indicating up or down. At near-vertical diagonals, retain a visible horizontal cue without collapsing the pose into the adjacent cardinal. Progress gradually across the row boundaries and loop wrap.

Cardinals, wrong quadrants, reversals, conspicuous jumps, clipping, and real interior holes block acceptance. Slightly uneven angle spacing is a reviewed warning when the ordered loop stays coherent. A continuity metric may flag normal space between limbs; inspect it before regenerating. Never dismiss a real torso seam as a harmless gap.

## Repair handoff template

```text
Job: one row ID from the actual manifest
Observed failure: visible evidence at normal pet size
Failure class: semantics / identity / geometry / extraction / continuity
Preserve: approved identity, exact mark, scale, baseline, references
Change: the smallest concrete pose or pipeline condition that caused failure
References: every manifest input, with its role; previous row only if useful
Acceptance: named visible cues and applicable deterministic checks
Return: selected source path and concise QA evidence; no manifest edits
```

The parent records the attempt and validates it. For a gaze repair, regenerate the whole coherent row, not a pasted single-cell replacement. Stop when the mandatory gates pass; optional polish should not restart a successful run.

## Completion and recovery

Report what is generated, validated, installed, and published separately. Do not promise real-time host status updates or full access to other chats from this skill. If cleanup is denied, preserve the artifacts, report that limited outcome, and do not retry through another deletion mechanism. Keep prompts or recovery evidence the user requested.
