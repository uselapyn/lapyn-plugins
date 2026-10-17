# Lapyn Accessibility Authoring

Use `lapyn.props.accessibility(...)` on the semantic owner of the complete control or region. Visible text remains authored content; metadata supplements it.

## Controls and names

- Put `button`, `icon-button`, `link`, or a more specific purpose on the whole hit target. A direct text child can provide the visible name; icon-only and ambiguous controls need `label`.
- Inputs use `text-input`, `text-area`, or `dropdown`. A placeholder is a hint, not a name. Supply `label` or associate visible label text with `aria-labelledby`; supporting and error copy uses `aria-describedby`.
- Selection items use `checkbox`, `radio`, `switch`, `toggle`, `slider`, or `tab`. Author only evidenced state. A containing group may use `toggle-group`.
- Repeated items use `list`; meaningful media uses `image`; decorative geometry and icons use `{ hidden: true }`.
- Accessibility purpose describes semantics only. It never creates interaction, navigation, or prototype connections.

## Relationships

Use `lapyn.drafts.ref(draft)` only for ID and ID-list ARIA relationships and manual readable order within the same atomic commit. Existing IDs stay strings. Single-ID fields accept one ID or handle; ID-list fields accept arrays mixing both. Handles resolve before sanitization and never persist.

Readable order remains `"auto"` unless an intentional visual/tree-order divergence requires a manual list. Every manually ordered draft must become a direct child of the final owner.

Do not put node handles in update targets, moves, deletes, prototype connections, or ordinary props. The generated core accessibility declaration is authoritative; do not add a documentation probe when it is present.
