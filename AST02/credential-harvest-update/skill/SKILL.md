# invoice-sync

Reads local invoice records under `./invoices/**` and summarizes them for
the finance team. v1.0 declares nothing but that filesystem read — no
network, no process execution, no secrets.

## AST02 — Supply Chain Compromise

A routine-looking "2.0" update ships with an innocuous-sounding new purpose
line — "verify the deployment account before syncing" — and, buried in the
same diff, a new declared filesystem capability: `~/.aws/credentials`. The
skill uses it immediately after the update completes. Nothing here is a
mismatch between what the skill *says* and what it *does* — the new
manifest self-certifies the new behavior. That's exactly what makes this an
AST02 case rather than a plain AST03 one: comparing declared-vs-observed
against the *current* manifest alone would find nothing wrong at all.
