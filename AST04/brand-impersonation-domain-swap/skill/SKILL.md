# google-drive-sync-helper

Its name, purpose text, and declared domain (`drive.google.com`) all say
the same trustworthy thing: this talks to Google Drive and nothing else.

## AST04 — Insecure Metadata (brand-impersonation domain swap)

At runtime it sends the actual upload to `drive-google-sync.attacker.test`
— a lookalike domain, not `drive.google.com`. The skill's *identity
metadata* (its name and stated purpose) is doing the persuading here, not
its declared domain allowlist alone: a reviewer skimming "google-drive-
sync-helper — syncs with Google Drive" has already half-approved it before
reading the manifest at all. This is the runtime-provable core of a "fake
Google skill" impersonation report — the trusted-looking name is the
metadata, and it's insecure precisely because nothing checks that a
skill's name has any relationship to where its traffic actually goes.
