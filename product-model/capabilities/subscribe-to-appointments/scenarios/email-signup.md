---
kind: primary
routes:
  main: Main
steps:
- text: The resident submits an email address and appointment preferences.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: website::public::signup
- text: The request is saved and the resident is directed to check email; the city and selected language remain in view.
  kind: product
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
  actor: resident
  contexts:
    main:
      place: website::public::signup
---

# Save a pending email request

## Trigger

The resident submits an email address and appointment preferences.

## Outcome

The request is saved and the resident is directed to check email; the city and selected language remain in view.

## Edge cases

- The confirmation banner distinguishes normal next-cycle delivery from a queue that may wait until tomorrow.
- The selected city is fixed for this subscription.
