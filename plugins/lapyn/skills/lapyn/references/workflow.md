# Lapyn Execution Workflow

Use for source-dependent and complex mutations.

## Route

- Prompt-only: one mutation and commit.
- Source-dependent: discovery, model composition, then guarded mutation.
- Complex: three to six semantic mutation checkpoints for independent regions, repeated nontrivial components, or a large program.

Each mutation commits once atomically.

## Discover

Simple work returns evidence once. Complex work uses at most two reads:

1. Return project ID, revision, a compact inventory (`id`, `name`, `kind`, `parentId`, `screenId`, `childIds`), and needed collection counts.
2. After selection, get chosen records and required collections only.

`nodes.get` batches up to 200 IDs; `findAll` owns paging. During discovery, never return full subtrees/collections, repeat reads, queue commands, commit, classify with regex, or project styles.

## Compose and checkpoint

Choose sources and hierarchy outside the `code` tool. Track `{ projectId, revision, ids, completed }`. Commit regions, not nodes. Create the shell, then one canary before repetition. Keep stable `localId`s and carry `revision`/`localIds` forward. Do not alter authored names, metadata, or canvas content for progress.

For each checkpoint, reopen with expected authority, reread only used known sources, author, and commit once. Do not search, resolve selection again, or replay completed checkpoints; do not probe `lapyn.docs` for core contracts.

After visual work, reopen at the latest revision and render requested screens at 2x, together when practical. Return compact metadata; do not routinely reread descendants.

Inspect every `downloadUrl` with an image-capable tool; metadata is not visual evidence. Check overflow, clipping, assets, wrapping, contrast, spacing, and repetition. Correct a clear defect once and rerender affected screens; if still defective, stop and report it.

If inspection fails, keep successful commits and report verification incomplete; do not substitute a broad read. Use targeted reads for discovery/reuse, unknown-write recovery, and explicit nonvisual invariants. `read.validateProjection` compares observations; it does not inspect rendering.

Routine complex visual work uses one or two discoveries, three to six mutations, one render check, and at most one correction plus rerender.

## Recover

- Correct a failed checkpoint once; a failed call writes nothing.
- On revision mismatch, reconcile once and retain valid completed targets.
- For an unknown write outcome, inspect explicit checkpoint targets before retrying.
- If correction fails, report completed, failed, and remaining checkpoints.
