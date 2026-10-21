---
kind: primary
routes:
  main: Main
steps:
- text: The resident submits a service and appointment preferences on a verified phone.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::device::form
- text: The alert is active immediately and the app opens My alerts.
  kind: product
  entities:
  - entity: app-alert
    effect: creates
    to: Active
    facts:
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
    - Legacy special consent
    - Active
  actor: resident
  contexts:
    main:
      place: mobile-app::device::form
---

# Create a live app alert

## Trigger

The resident submits a service and appointment preferences on a verified phone.

## Outcome

The alert is active immediately and the app opens My alerts.
