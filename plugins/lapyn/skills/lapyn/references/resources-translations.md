# Lapyn Resources and Translation

References are reusable variant-aware colors, numbers, strings, booleans, rich text, assets, enums, or sizing values. Persisted bindings use `{ type: "ref", ref }`. Translations are locale-aware text resources whose bindings use `{ type: "translation", key }`. Handles returned by `create` are transaction-local and may be assigned only within the same commit.

Read existing collections before choosing set, variant, locale, or entry IDs. Use `editor.read.collections` only for the requested resource families, and use focused translation reads when known keys are sufficient. Reuse existing identifiers rather than creating parallel resource structures.

## Translating existing content

Translation is a source-dependent workflow: discover first, translate at the model layer, then mutate against the exact project revision.

Discovery collects the complete selected subtree with an explicit `findAll` budget. Authored text lives at `props.text.value`; literal content is normally a rich document. Collect existing translation bindings separately from literal text, deduplicate keys, and read canonical entries with `editor.read.translationEntries`. Report literal nodes rather than silently converting them unless conversion was requested.

Translate complete sentences outside generated JavaScript. For rich values, preserve block types, heading levels, list nesting, run order, marks, and links; change only visible run text. Consolidate brands, proper nouns, identifiers, and language-neutral tokens into one clarification before mutation.

The mutation reopens with the discovered project and revision. Reuse an existing locale whose ID or authored name represents the requested language; otherwise add it once. Skip values already present in the target locale. Updating a shared translation key affects every bound node, including nodes outside the originally selected subtree.

When converting requested literal text, preserve the canonical rich blocks as the source locale and bind the new translation handle in the same commit. Never flatten rich text, fabricate other locales, or author `props.text.value` directly.

Call `lapyn.docs.describe('editor.references')`, `editor.translations`, and `editor.read` for exact current signatures and focused examples.
