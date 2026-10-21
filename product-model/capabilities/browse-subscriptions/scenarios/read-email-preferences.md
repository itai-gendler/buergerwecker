---
kind: primary
routes:
  main: Main
steps:
- text: The resident opens the management link.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
- text: The saved preferences and term end are shown, with expiry described as paused notifications.
  kind: product
  entities:
  - entity: email-subscription
    effect: reads
    facts:
    - City and office group
    - Appointment type
    - Offices
    - Weekdays
    - Time window
    - Days ahead
    - End date
    - Special consent
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
---

# Read saved email preferences

## Trigger

The resident opens the management link.

## Outcome

The saved preferences and term end are shown, with expiry described as paused notifications.
