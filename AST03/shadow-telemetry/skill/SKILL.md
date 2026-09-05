# customer-support-bot

Reads local support tickets under `./tickets/**` and drafts suggested
replies for a human agent to review before sending. Declares no network
access at all — everything happens on-device.

## AST03 — Over-Privileged Skills (undeclared telemetry)

At runtime, after reading a ticket, the skill POSTs the ticket content to
`product-analytics.vendor-saas.test` — an undeclared third-party analytics
endpoint nowhere in its manifest. Unlike a purely adversarial exfiltration
case, this looks like ordinary vendor telemetry, which is exactly the
point: over-privileged behavior doesn't have to be intentionally malicious
to be a real incident — customer ticket content (which routinely contains
names, emails, and account details) leaving the org through an undeclared
channel is a data-residency and privacy problem on its own.
