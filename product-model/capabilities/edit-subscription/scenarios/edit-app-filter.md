---
kind: primary
routes:
  main: Main
steps:
- text: The resident saves new alert preferences.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::device::form
- text: The app alert has the new filter and selected language; the app returns to the preceding view.
  kind: product
  entities:
  - entity: app-alert
    effect: changes
    facts:
    - Appointment type
    - Offices
    - Weekdays
    - Time window
    - Days ahead
    - Language
    - Cadence
  actor: resident
  contexts:
    main:
      place: mobile-app::device::form
---

# Save an alert filter

## Trigger

The resident saves new alert preferences.

## Outcome

The app alert has the new filter and selected language; the app returns to the preceding view.
