---
kind: primary
routes:
  main: Main
steps:
- text: The resident opens My alerts.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::device::alerts
- text: Each saved alert shows its selection and end date, with currently matching snapshot slots when available.
  kind: product
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
  - entity: free-slot
    effect: reads
    facts:
    - City and office group
    - Appointment type
    - Office
    - Date
    - Time
    - Last checked
  actor: resident
  contexts:
    main:
      place: mobile-app::device::alerts
---

# Read the phone’s alerts

## Trigger

The resident opens My alerts.

## Outcome

Each saved alert shows its selection and end date, with currently matching snapshot slots when available.

## Edge cases

- Expired alerts offer Keep looking.
- A truncated or absent snapshot does not justify saying no matching slots exist.
- A list read failure is displayed with a retry action.
