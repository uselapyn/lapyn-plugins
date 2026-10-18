# Lapyn Visual Authoring

## Direction and hierarchy

Decide the job, user, tone, primary action, reading order, and dimensions before coding.

## Fidelity and visual direction

Treat “quick”, “sketch”, “rough”, and “concept” as scope/refinement limits, not grayscale requests. Use low fidelity or wireframes only when explicitly requested.

Treat design as a coupled visual language. Establish the applicable parts of a compact system:

- **Space:** margins, padding, gaps, alignment, grid, density, and control sizing.
- **Form:** proportions, shapes, corners, borders, effects, and states.
- **Theme:** semantic background, surface, text, accent, and status colors with readable contrast.
- **Type and content:** hierarchy, weight, line height, letter spacing, voice, and terminology.
- **Icons and imagery:** one consistent style and treatment, including intentional omission.

Make decisions reinforce one another; add no filler.

## Contextual design continuity

Activate continuity for duplication, continuation, extension, and insertion from an explicit target or established flow. Ignore unrelated content and arbitrary active screens. Restyle or from-scratch intent overrides continuity.

Prefer canonical records/resources, then previews, then inference. Report unreadable sources; ask when candidates differ materially.

Preserve by operation:

- **Clone:** visible hierarchy, macro layout, content, treatment, and states; style additions from semantic analogues.
- **Continue:** visual vocabulary, voice, interaction conventions, density, and rhythm while adapting structure.
- **Insert:** containing layout and the nearest analogue for the element’s semantic role.
- **Targeted edit:** only required nodes/properties; preserve unrelated geometry, layout, style, content, interactions, identities, and bindings.

Never infer data, relationships, or prototype destinations from appearance. Identify analogues before copying; `.read()`/`.from()` may return neutral values. Adapt with `.from(source, overrides)` and never mix sources or blanket-catch failures.

## Layout and sizing

Specify complete `flow`, `gap`, `padding`, `align`, and `justify` for critical layouts. Omitted geometry hugs content; omitted spacing is zero.

Author intentional margins, padding, and gaps. Parents own child spacing; controls own label/icon padding.

- **Fill:** consume parent-supplied space.
- **Hug:** let content or children determine size.
- **Fixed:** reserve for icon, touch-target, or artwork invariants.
- **Screens:** fix a screen's width to the device; its height hugs the content unless a fixed viewport is explicitly
  requested. Don't shrink content to fit a device height.
- **Fill factor:** use only for intentional distribution between fill siblings.

Express these as complete axis values: `width: lapyn.sizing.fill()`, `height: lapyn.sizing.hug()`, or `height: lapyn.sizing.fixed(52)`. Do not split one axis across a numeric value and a separate mode.

A fill child cannot size a hugging parent on the same axis. Check constraints, fixed children, gaps, padding, and remaining space. Text and child alignment differ.

For `flow: "stack"`, parent `align`/`justify` supply horizontal/vertical defaults. Override a child with `lapyn.props.alignment({ horizontal, vertical })`. Generic `self` is the row/column cross-axis override; `transform.offset` is post-layout displacement, not centering. See `sdk_reference` with topic `props.alignment` for a centered-stack example.

## Visual semantics

Give screens and visible surfaces deliberate fills; leave structures transparent. `lapyn.props.opacity` (0–100) dims descendants; use fill alpha (0–1) for translucent surfaces with opaque content.

Modifier arrays are ordered; blur or clip encloses later entries. Clip only intentionally bounded content. Preserve evidenced clips, put outside shadows before them, and use a larger owner or wrapper for bleed.

Choose assets by role:

- **Vector:** use evidenced vectors, then bounded provided/purpose-authored SVG, then portable paths. Set intentional SVG dimensions and report warnings.
- **Nodes:** use nodes for layout, surfaces, text, controls, and independent stateful parts. Use primitives only when simple geometry benefits from separate editing or responsive layout.
- **Images:** once supported, use dedicated raster assets. Until then, purpose-made flat illustrations are artwork
  (use SVG); do not fake photographs or other raster stand-ins with primitives/SVG, and do not invent an API.

Keep visible text as text. Never use emoji/Unicode as interface icons. Label meaningful icon-only controls and hide decoration.

## Pre-checkpoint check

Before each mutation checkpoint, confirm only relevant invariants:

- Requested fidelity and continuity are correct without placeholder scaffolding.
- Fills, opacity, component treatments, and states are intentional and evidenced.
- Layout constraints resolve; margins, padding, gaps, text, and controls fit their bounds.
- Any clip is intentional or evidenced, and its order preserves exterior effects while containing the required content.
- Icons/artwork use the right asset type; SVG dimensions are intentional; no primitive assembly or unsupported image API substitutes for an asset.
- Numeric values follow live SDK units; nested nodes use layout/alignment or intentional offsets, not canvas placement.
- Visible labels remain text; semantic owners carry accessibility; decoration is hidden.
- Space, form, theme, type/content, states, and imagery form one coherent direction without filler.

## Rendered verification

For final verification, render requested screen roots at 2x and inspect every artifact's pixels. Do not expand to unrelated screens.

Inspect for overflow, clipping, cropping, missing assets, wrapping, contrast, spacing, and inconsistent repeated screens. Rendered evidence covers appearance only; use targeted reads for accessibility, connections, references, or translations.

For a clear defect, make one targeted correction and rerender affected screens. If rendering or correction fails, preserve successful commits and report the result as unverified or defective. Never substitute a node-tree dump for rendered evidence.
