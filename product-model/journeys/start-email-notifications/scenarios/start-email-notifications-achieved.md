---
kind: primary
result: achieved
routes:
  main: Email
steps:
- text: The resident saves appointment preferences.
  kind: actor
  actor: resident
  capability: subscribe-to-appointments
  entities: &id001 []
  contexts:
    main:
      place: website::public::signup
- text: The Product saves the email subscription pending confirmation.
  kind: product
  actor: resident
  capability: subscribe-to-appointments
  entities:
  - entity: email-subscription
    effect: creates
    to: Pending
    facts:
    - Email address
    - City and office group
    - Appointment type
    - Offices
    - Weekdays
    - Time window
    - Days ahead
    - Language
    - End date
    - Last notified
    - Cadence
    - Check-in sent
    - Special consent
    - Confirmation sent
  contexts:
    main:
      place: website::public::signup
- text: The resident follows the confirmation link.
  kind: actor
  actor: resident
  capability: confirm-email-subscription
  entities: *id001
  contexts:
    main:
      place: website::subscription::subscription
- text: The Product activates the email subscription.
  kind: product
  actor: resident
  capability: confirm-email-subscription
  entities:
  - entity: email-subscription
    effect: changes
    from: Pending
    to: Active
    facts: []
  contexts:
    main:
      place: website::subscription::subscription
---

# Activate the requested email search

## Trigger

The resident submits a new email search.

## Outcome

The saved search is active after its confirmation link is followed.
