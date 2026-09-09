---
name: plan2model-su
description: Create detailed, editable, render-ready SketchUp interior models from floor plans and interior references. Use for plan-to-model interior design or refinement, not image-only rendering.
---

# Plan2Model-SU

Deliver an editable `.skp` interior suitable for design development and rendering.

## Input gate

- Require a floor plan and a design direction. Prefer reference images and known dimensions.
- If only a floor plan is provided, pause modeling and ask together: "What interior style do you want, and do you have reference images?"
- Use user-provided references first. If the user has none, or still gives only a style after references are requested, search the web for a small, coherent reference set. Inspect the images; retain source links and the design cues adopted.
- If free design is authorized, choose a suitable style and gather references without another approval round.
- Do not start detailed modeling without user references or a defined style plus gathered references. If images cannot be accessed, request accessible references and state the blocker.

## Source hierarchy

| Source | Controls |
|---|---|
| Floor plan | Structure, room boundaries, walls, openings, circulation, furniture position, orientation and scale |
| Interior references | Hard finishes, cabinetry details, furniture form, materials, lighting, colors and soft furnishings |
| Inference | Missing information only; keep assumptions brief and explicit |

Never reshape the plan to imitate a reference. Resolve conflicts in favor of the plan; ask only when ambiguity materially changes the result. Known dimensions override visual estimates.

## Workflow

1. **Read and calibrate.** Identify rooms, walls, openings, fixed elements and furniture. Establish units and scale from labeled dimensions; cross-check another dimension when available. Ask for a reliable dimension when scale cannot be established; use provisional estimates only if authorized. Record missing heights, thicknesses and other necessary assumptions once.
2. **Set design cues.** Summarize the reference palette, hard finishes, furniture silhouettes, lighting and textiles. Assign coherent cues to each room; avoid unrelated reference styles.
3. **Build the shell.** Model walls, floors, ceilings, doors and windows with actual openings and thickness. Verify boundaries and dimensions before adding detail. Preserve the plan's layout.
4. **Fit and refine.** Locate furniture using temporary masses, check circulation, then replace or refine every placeholder. Model recognizable silhouettes and construction: cushions, arms, legs, joinery, cabinet gaps and hardware where visible. Add appropriate skirting, trim, ceiling features, fixtures, curtains and textiles. Reuse suitable assets after checking scale, materials and editability.
5. **Prepare for rendering.** Apply materials at believable texture scale and orientation. Check face orientation and shading; add useful interior camera scenes. If a renderer is specified and available, prepare compatible materials and lights and verify with a preview. Otherwise prepare native geometry, materials and light fixtures, and identify remaining renderer-specific setup.
6. **Inspect and deliver.** Run the checks below, fix failures locally, save and reopen the final model when supported, and report only verified completion.

## Modeling standard

- Use named Groups for separate assemblies and Components for repeated objects. Make a component unique before an instance-specific edit. Keep raw edges/faces Untagged; apply organizational tags to containers.
- Maintain realistic proportions, seat/worktop heights, reach, door swings, drawer travel and walking clearances. Flag plan conflicts rather than silently relocating furniture or changing structure.
- Balance low-poly geometry with visible quality: spend detail on silhouettes, close views, joints and small bevels; simplify hidden surfaces and instance repetition. Avoid excessive tessellation and flattened, uneditable imports.
- Blocky placeholder furniture is allowed only during layout. Final furniture must have reference-appropriate form and visible construction detail. Simple geometry is acceptable when it represents the actual design.

## QA and completion

- Compare plan/top view against the source: dimensions, openings, furniture positions, orientations and scale agree.
- Inspect room views and representative close-ups: no placeholders, accidental intersections, floating objects, reversed visible faces, flicker or visibly faceted curves.
- Check ergonomic clearances and operation of doors, drawers and seating; disclose unresolved constraints.
- Check Group/Component separation, repeated instances, tag visibility, materials, texture mapping and missing assets. Remove unused construction helpers and purge unused resources after checking dependencies.
- Deliver the saved `.skp`, overview and detail views, necessary texture dependencies, and a short note of assumptions, reference links and unresolved issues. Completion requires all requested rooms furnished and detailed, editable organization, and QA passed; unresolved required work means partial completion.
- If the available tools cannot create or verify a SketchUp model, state that limitation. Do not present scripts, screenshots or another format as a completed `.skp`, or claim a tested render without a render test.
