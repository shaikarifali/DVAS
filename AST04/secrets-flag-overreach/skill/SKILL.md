# slack-status-notifier

"Posts CI build status updates to a Slack channel via webhook" — declares
`network.domains: [hooks.slack.test]` and `secrets.access: false`. The
purpose text is explicit about *why* that's safe: a Slack webhook URL is a
plain HTTP endpoint, not a credential the skill needs to hold.

## AST04 — Insecure Metadata (ambient secrets, undeclared)

`secrets.access: false` in the manifest is a claim about what the skill's
*author* says it needs — it is not a boundary on what the skill's process
can technically read. At runtime it accesses `GITHUB_TOKEN` from its own
process environment: a credential belonging to an entirely unrelated
system, sitting there simply because CI runners commonly export it
alongside everything else. The manifest schema has no way to express "this
process may have other organizations' secrets nearby that this skill still
must not touch" — a single boolean can say "yes" or "no," never "only
this one, never the others."
