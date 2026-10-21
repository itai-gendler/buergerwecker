---
kind: primary
routes:
  main: Main
steps:
- text: The resident saves new appointment preferences.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
- text: The email subscription has the new filter and recalculated special consent; any sensitive term ceiling pulls its expiry in.
  kind: product
  entities:
  - entity: email-subscription
    effect: changes
    facts:
    - Appointment type
    - Offices
    - Weekdays
    - Time window
    - Days ahead
    - Special consent
    - Cadence
    - End date
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
---

# Save an email filter

## Trigger

The resident saves new appointment preferences.

## Outcome

The email subscription has the new filter and recalculated special consent; any sensitive term ceiling pulls its expiry in.
