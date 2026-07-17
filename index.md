# Homie Scheduler — Privacy Policy

_Last updated: July 17, 2026_

Homie Scheduler is a household scheduling app for families. This policy
explains what data the app handles, where it goes, and what stays on your
device. The short version: your household's data lives on your devices and
in a private synced copy only your household can read; nothing is sold,
shared for advertising, or used to train AI models; voice never leaves
your device as audio.

## What the app stores

- **Account data**: an email address and password (password handled by our
  authentication provider, Supabase — we never see it) for each adult or
  invited member who signs in.
- **Household data you enter**: family member names and roles, events and
  schedules, routines, task lists, grocery lists, and saved places
  (addresses and map coordinates). This is stored on your device and — if
  you enable sync — in a Supabase-hosted database (Supabase Inc., cloud
  infrastructure in the United States), where **row-level security
  restricts every record to signed-in members of your own household**.
  App developers do not read household content in the normal course of
  operation; like any hosted database, it is technically accessible to
  the database administrator and to Supabase as the infrastructure
  provider.

## What leaves your device, and why

- **Schedule text you type or dictate** can be sent to Anthropic's Claude
  API to be turned into a structured draft event. If your household uses
  its own Anthropic API key, text goes directly from your device to
  Anthropic. Otherwise it passes through our proxy service, which
  forwards it and **stores only a count of requests per account** (for
  rate limiting) — never the text itself. Anthropic processes it under
  its API terms, which do not permit training on API data. Parsing also
  works fully offline with reduced quality; an AI failure never blocks
  the app.
- **Voice capture is transcribed on your device** by the operating
  system's speech recognition. Audio is never uploaded. Only the
  resulting text is handled as above.
- **Addresses you save** are sent to a geocoding service (OpenStreetMap
  Nominatim) to find map coordinates, and **pairs of coordinates** are
  sent to a routing service (OSRM) to estimate travel times. These
  requests carry no account identity, and results are cached.
- **If the app crashes or hits an error**, a diagnostic report (stack
  trace, device model, OS version, app version) is sent to Sentry so we
  can fix it. These reports are scrubbed of message text before sending
  and never include household content or anything you captured.

## What we do NOT do

- No advertising, no trackers, no analytics SDKs, no selling or
  sharing of data with data brokers.
- No training of AI models on your data, by us or (per their API terms)
  by Anthropic.
- No background location tracking. The app never reads your device's GPS
  location; it only geocodes addresses you type in.

## Children

Homie Scheduler is designed for families, including children. **A child
cannot create an account on their own**: child accounts can only join a
household through an invite code created by a signed-in adult of that
household — creating that invite is the parent's or guardian's consent
for the child's use of the app. Invite codes for restricted (child)
accounts carry limited permissions set by the adult. If you believe a
child's account was created without parental consent, contact us and we
will delete it.

## Your data, your control

- **Access and deletion**: household adults can edit or delete any
  household record in the app. Removing a member (or a member leaving)
  ends their access. To delete an account or an entire household's synced
  data, contact us at the address below and we will remove it from the
  hosted database.
- **Local-only mode**: the app works without sync; without it, household
  data never leaves your devices except for the AI parsing and map
  lookups described above.
- **Backups you export are yours** and are stored wherever you put them.

## Service providers

| Provider | Purpose | What they receive |
|---|---|---|
| Supabase | account auth + household sync | email, password (hashed), synced household data |
| Anthropic (Claude API) | turn captured text into draft events | the text you capture, via our pass-through proxy or your own key |
| Resend | password-reset emails | your email address |
| Sentry | crash + error diagnostics | error reports: stack traces, device & OS version (NOT household content or captured text) |
| OpenStreetMap Nominatim | address → coordinates | address text you save |
| OSRM / FOSSGIS | travel-time estimates | pairs of map coordinates |

## Changes

We will update this page when the app's data handling changes and adjust
the "last updated" date above. Material changes will be called out in the
app's release notes.

## Contact

Questions or data requests: **homie.family@protonmail.com**
