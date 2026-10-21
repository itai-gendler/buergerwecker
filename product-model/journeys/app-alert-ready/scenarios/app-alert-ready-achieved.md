---
kind: primary
result: achieved
routes:
  main: Main
steps:
- text: The resident saves the selected service and filter.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::device::form
  capability: subscribe-to-appointments
- text: The Product saves the app alert and opens My alerts.
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
      place: mobile-app::device::alerts
  capability: subscribe-to-appointments
- text: The resident reads the new app alert and its end date.
  kind: actor
  entities:
  - entity: app-alert
    effect: reads
    facts:
    - City and office group
    - Appointment type
    - Offices
    - Weekdays
    - Time window
    - Days ahead
    - End date
  actor: resident
  contexts:
    main:
      place: mobile-app::device::alerts
  capability: browse-subscriptions
---

# Create an alert and land in My alerts

## Trigger

The resident wants a new alert for the selected service.

## Outcome

The new alert is active and visible in My alerts.
