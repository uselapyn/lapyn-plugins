---
name: lapyn
description: Operate an authorized Lapyn design through Code Mode MCP, or diagnose connection failures. Do not use for ordinary repository work or generic debugging.
---

# Lapyn

Use the connected `code` tool as the authority for design state and mutation. Generated JavaScript imports only `{ lapyn }` from `lapyn-sdk.js`; the `sdk_reference` tool owns exact signatures; before authoring, read the topics or groups you use (`props.layout`, `props`, or `all`).

## Choose the execution path first

- **Pure read:** use one read-only call and return the requested evidence.
- **Simple prompt-only mutation:** when every decision comes from the prompt and the result is one bounded composition, use one call and one `editor.commit()`.
- **Source-dependent mutation:** use discovery → analysis/clarification → guarded authoring for work derived from or placed relative to existing content.
- **Complex mutation:** for multiple independent regions, repeated nontrivial components, or a large program, use three to six semantic mutation checkpoints. Read [references/workflow.md](references/workflow.md).

Never combine source discovery and mutation. Analyze canonical evidence outside the `code` tool, then mutate by rereading only chosen IDs and committing once per checkpoint. Carry returned revisions and local ID mappings forward; never replay completed checkpoints.

At the start of every call, assert the exact SDK fingerprint shown in the live tool description. A mismatch means the MCP connection is stale; reconnect rather than adapting code to mixed declarations.

## Connected design rules

- Resolve context only for “here”, “this”, selection, active-screen, or viewport-relative intent. Explicit targets win; pass the named user or ask when matches are ambiguous.
- Render user-facing previews at 2x unless another density is requested; use 1x for logical-pixel export. Inspect every requested preview's pixels before claiming visual verification.
- Create ordinary prompt-only work under `editor.project.root` without placement. Never silently fall back for selection- or viewport-relative work.
- Use `lapyn.props` for authored properties. Every builder except `compose` supports exact reuse through `.read(source)` and `.from(source, overrides?)`. Adapt copied groups with `.from`; never compose another fragment from the same builder. These are not discovery predicates.
- Pass atomic `lapyn.sizing.fixed(value)`, `lapyn.sizing.fill(factor?)`, `lapyn.sizing.hug()`, or sizing references as `width`/`height`; never split an axis into scalar, mode, or factor fields.
- Use `lapyn.color.rgb`, `.hex("#RRGGBB", alpha?)`, or `.oklch`; never encode alpha as eight-digit hex.
- In stacks, parent `align`/`justify` set horizontal/vertical defaults. Override children with `props.alignment({ horizontal, vertical })`; `self` is for row/column cross-axis alignment and `transform.offset` is deliberate post-layout displacement.
- Import bounded provided/authored SVG icons/artwork with `lapyn.props.vector.svg(source)`. It yields intrinsic-size vectors; report warnings; markup never persists.
- Readable groups may contain neutral defaults. Never infer visibility from read success, blanket-catch failures, walk keys heuristically, convert exact colors, average radii, or invent fallbacks.
- `lapyn.props.opacity` (0–100) dims the whole node and its descendants. Use the fill color alpha (0–1) for a translucent background.
- Use `lapyn.richText` plus `drafts.text` or `nodes.update({ content })` for text. Do not author `props.text.value`, Markdown, or HTML.
- Modifier arrays are ordered; preserve them with `stack`, `prepend`, `append`, `replaceAt`, and `removeAt`. Blur and clip enclose later entries. Clip only intentionally bounded content, put outside shadows before the clip, and use a wrapper for bleed. Blur is foreground, not backdrop.
- Keep visible labels in text nodes. Add authored accessibility labels to icon-only or ambiguous controls; hide decorative children. Accessibility metadata never replaces visible content or implies behavior.
- Use `drafts.ref` only for draft ARIA ID relationships and manual readable order in the same atomic commit. Existing IDs remain strings.
- Omitted geometry is neutral: content hugs, structures are transparent, and spacing is zero. Author visible surfaces and fixed dimensions only when required. Parents own padding and gaps.
- Mutations require an explicit user request and an authenticated credential that permits writes. Refuse writes when the target project is ambiguous or the credential is read-only.

## Route only the references required

- Read [references/visual-authoring.md](references/visual-authoring.md) for complete screens, redesigns, onboarding, landing views, or any mutation that duplicates, continues, extends, or inserts into an existing composition.
- Read [references/accessibility.md](references/accessibility.md) for relationships, manual reading order, or nontrivial semantics.
- Read [references/resources-translations.md](references/resources-translations.md) only when mutating references or translations, or when translating existing content. Collection inspection alone uses the core declaration.
- Read [references/recovery.md](references/recovery.md) for unfamiliar structured failures, connection failures, or revision recovery.
- [references/design-mcp.md](references/design-mcp.md) is a compact compatibility index, not a required general read.

## Connection operation

Use the MCP endpoint configured by the plugin host; never substitute or probe another environment. Reconnect after SDK or tool-description changes. On failure, report the authentication or transport error; reconnect or reauthorize when the credential expired or was revoked.
