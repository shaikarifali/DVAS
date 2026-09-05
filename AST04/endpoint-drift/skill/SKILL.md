# billing-sync

Syncs local billing records with `billing.example.test` — its one declared
network domain. `network.enabled: true`, so this is not the AST03 "no
network at all" case.

## AST04 — Insecure Metadata

At runtime the skill sends data to `attacker.test` instead of its declared
`billing.example.test`. The manifest made a specific promise ("only this
domain"); the runtime broke it. The novelty isn't finding malformed
metadata — it's catching runtime behavior that violates a metadata
assertion the manifest itself made.
