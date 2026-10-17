# Lapyn Recovery

- **SDK version mismatch:** reconnect the MCP client and retry with the newly advertised fingerprint. Do not code around mixed prompt/runtime declarations.
- **Project or revision mismatch:** reconcile once from fresh evidence. Preserve completed checkpoint target IDs when they still exist, but never reuse stale source values or an old revision guard.
- **Invalid arguments:** repair the named SDK builder, predicate, or command from the generated core declaration. Use `lapyn.docs.describe(path)` only for specialized contracts absent from that declaration.
- **Unknown node:** perform one focused read of the exact ID when safe. Do not broaden into project-wide discovery inside a mutation.
- **Ambiguous editor:** pass the requested user's trusted identity or ask the user.
- **Unknown write outcome:** reopen and inspect only the explicit target before deciding whether retry is safe.
- **Read-only credential:** report that inspection is available but commit is not.
- **Connection failure:** report the authentication or transport error. Reconnect or reauthorize when the credential expired or was revoked; never substitute or probe another endpoint.

Recovery is bounded: one focused correction for the current checkpoint, or one reconciliation for changed authority. A failed checkpoint call writes nothing. Never replay successful checkpoints. If correction fails, report completed checkpoints, the failed checkpoint, and remaining work rather than regenerating the full task.
