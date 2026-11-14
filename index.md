# Homie — Privacy Policy

_Last updated: November 14, 2026_

Homie is a household scheduling app for families, provided by
**Homie.Family** ("we", "us"). This policy explains what data the app
handles, where it goes, and what stays on your
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

- **A notification token, if you turn nudges on.** Turning on
  leave-time nudges registers an anonymous push identifier for that
  device, so other devices in your household can tell it that a plan
  moved. It identifies a phone, not a person, and it is stored only while
  nudges are switched on.

- **Which version of these terms you agreed to, and when.** When an adult
  account agrees to the Terms of Use and this policy — by creating the
  account, or by tapping Continue when the app asks after they change — our
  server keeps a note of which version (the "last updated" date) and the
  time. Nothing else is in it, and it is kept so we can show what you agreed
  to and when. Children's accounts keep none (see Children).

## What leaves your device, and why

- **Schedule text you type or dictate** can be sent to Anthropic's Claude
  API to be turned into a structured draft event. It always passes through
  our proxy service, which forwards it and **stores only a count of
  requests per account** (for rate limiting) — never the text itself.
  There is no setting for this and no key to enter. A device that is
  signed out — or an account whose email address hasn't been confirmed
  yet — does the parsing on its own, on the phone. Anthropic
  processes it under its API terms, which do not permit training on API
  data. Parsing also works fully offline with reduced quality; an AI
  failure never blocks the app.
- **Voice capture is transcribed on your device** by the operating
  system's speech recognition. Audio is never uploaded. Only the
  resulting text is handled as above.
- **Places you look up** go to Google Maps: the words you type while
  searching for a place, then the place you pick or the address you save,
  to find its address and map coordinates. **Travel times** come from
  Google Maps too: it receives a pair of map coordinates and, for a drive,
  when you plan to leave, so the time reflects traffic for that day and
  hour. The same pair of coordinates also goes to a routing service
  (Geoapify) for a rough time your device keeps to show while Google's
  answer loads. These requests contain no account identity — never who is
  going, never your schedule. Search results and Google's travel times stay
  on your device only briefly; the address and coordinates of a place you
  choose are kept with your household's places. Google handles what it
  receives under the [Google Privacy Policy](https://policies.google.com/privacy).
- **Where you are, but only while you search for a place.** When you look
  up a place to put on a plan, the app can ask for your device's location
  and send it to Google Maps as the centre of the search, so the nearest
  match ranks first. Permission is requested the first time a search needs
  it — never when you open the app — and you may decline, in which case
  your saved home address is used as the centre instead. On Android the
  app asks for approximate location only. The position is used to order
  that one list of results: it is not stored on our servers, not synced to
  your household, and never attached to a plan.
- **A "something changed" signal, if you turn nudges on.** Our server
  keeps a count of how many of these signals your account has sent in the
  past hour, so a malfunctioning device cannot flood your family's phones;
  the count holds no schedule content and ages out. Nudges
  themselves are worked out and scheduled entirely on your phone — the
  times you see are never calculated on a server. What travels is only a
  silent background message telling your other household devices that a
  plan changed and which household it belongs to, so each phone can update
  its own reminders. **It carries no plan titles, no names, no addresses,
  and nothing appears on screen when it arrives.** Delivery goes through
  Expo's push service and then Apple's or Google's notification systems,
  which see the device token and the message envelope.
- **Your email address, to confirm it and to reset a password.** When you
  confirm your address, or ask to reset a forgotten password, a one-time
  code is emailed to you (through Resend). Our server records that the
  address was confirmed and when — nothing else about the email.
- **Subscriptions, if your household has one.** Purchases are made and
  paid for entirely through Apple's App Store; we never see card or payment
  details. To know whether a household is subscribed, the app tells our
  subscription provider (RevenueCat) a random account identifier and which
  household the purchase is for, and RevenueCat tells our server when a
  subscription starts, renews, is cancelled or ends. None of this includes
  your schedule, names or addresses.
- **If the app crashes or hits an error**, a diagnostic report (stack
  trace, device model, OS version, app version) is sent to Sentry so we
  can fix it. These reports are scrubbed of message text before sending
  and never include household content or anything you captured.

## What we do NOT do

- No advertising, no trackers, no analytics SDKs, no selling or
  sharing of data with data brokers.
- No training of AI models on your data, by us or (per their API terms)
  by Anthropic.
- No background location tracking, and no location access at all except
  while you are actively searching for a place (see above). The app does
  not follow you, does not log where you have been, and keeps no location
  history.

## Children

Homie is designed for families, including children. **A child
cannot create an account on their own**: child accounts can only join a
household through an invite code created by a signed-in adult of that
household — creating that invite is the parent's or guardian's consent
for the child's use of the app. Invite codes for restricted (child)
accounts carry limited permissions set by the adult. Notifications are off
by default on every device, and the setting lives on a screen restricted
accounts cannot reach, so a child's device does not register a
notification token. Children are never asked to agree to the Terms of Use
or this policy, and no record of agreement is kept for a child's account —
if one was made before the account was known to be a child's, it is deleted
the moment an adult identifies the account as their child. If you believe a
child's account was created without parental consent, contact us and we
will delete it.

## Your data, your control

- **Access and deletion**: household adults can edit or delete any
  household record in the app. Removing a member (or a member leaving)
  ends their access. **You can delete your own account from inside the
  app** — Home tab → Delete account. It covers every household you belong
  to, and before you confirm, the app names each one and says what will
  happen to it. A household where another adult with full access remains
  stays with them (it belongs to the household, not to any one person);
  if you set it up, the adult who has been in it longest takes it over.
  Your personal details in it — your private task lists, your contact
  email, any invite codes you created — are removed. A household with no
  other adult who can run it is erased along with your account: everything
  synced in it, and the access of any children or helpers in it. Either
  way, the note of which terms you agreed to is deleted with your account.
  **You can also delete a household without deleting your account**, if
  you set it up and yours is the only account in it —
  Home tab → Delete household. Everything synced in it is erased for good,
  including your private task lists there, your contact email on its list
  and any invite codes for it; your account and its sign-in stay. You can
  also contact us at the address below.
- **Turning nudges off deletes the token** for that device, on our
  servers as well as on the phone. Deleting your account deletes every
  token registered to it.
- **Local-only mode**: the app works without sync; without it, household
  data never leaves your devices except for the AI parsing and map
  lookups described above.
- **Backups you export are yours** and are stored wherever you put them.

## Service providers

| Provider | Purpose | What they receive |
|---|---|---|
| Supabase | account auth + household sync | email, password (hashed), synced household data, the note of which terms version an adult account agreed to and when |
| Anthropic (Claude API) | turn captured text into draft events | the text you capture, via our pass-through proxy |
| Resend | password-reset and email-confirmation codes | your email address |
| RevenueCat | subscription status | a random account identifier, which household a purchase is for, purchase and renewal records (NOT household content) |
| Apple (App Store) | taking payment for subscriptions | your purchase, handled under Apple's own terms and privacy policy — we never see payment details |
| Sentry | crash + error diagnostics | error reports: stack traces, device & OS version (NOT household content or captured text) |
| Google (Google Maps Platform) | place search, address → coordinates, travel times | the words you type while searching for a place; the place you pick or address you save; while you search, your device's position (or your home's) as the search centre; pairs of map coordinates, plus a departure time for drives (NOT who is going or why) |
| Geoapify | a rough travel time kept on your device as a stand-in | pairs of map coordinates (NOT who is traveling or why) |
| Expo (Expo push service) | delivering the silent "a plan changed" signal to your other devices | your device's notification token + a signal naming which household changed (NOT plan titles, names or addresses) |
| Apple (APNs) / Google (FCM) | carrying that signal to the device | your device's notification token + the same signal |

## Changes

We will update this page when the app's data handling changes and adjust
the "last updated" date above. When a change is material, the app asks each
adult account once, the next time it opens, to read the updated policy and
agree to it before carrying on.

## Terms

Your use of Homie is also covered by our [Terms of Use](terms).

## Contact

Questions or data requests: **homie.family@protonmail.com**
