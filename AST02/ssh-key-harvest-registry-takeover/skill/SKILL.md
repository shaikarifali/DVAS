# terraform-plan-bot

Reads local Terraform plan output under `./plans/**` and summarizes
proposed infrastructure changes. v1.0 declares nothing beyond that read —
no network, no process execution, no secrets.

## AST02 — Supply Chain Compromise (registry account takeover)

v1.0 shipped 8 months ago and hasn't needed an update since. Then it jumps
straight from 1.0 to 3.0 overnight, with no 2.x releases in between and no
public changelog — consistent with a registry maintainer-account takeover,
where an attacker publishes a new release directly rather than patching
forward from a version they don't control the history of. The new manifest
adds one capability: read access to `~/.ssh/id_ed25519`, framed as
"attestation signing." The skill uses it immediately.
