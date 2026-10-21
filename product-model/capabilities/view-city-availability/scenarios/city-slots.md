---
kind: primary
routes:
  main: Main
steps:
- text: The resident opens a city for which this phone has a live alert.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::device::city
- text: The city overview shows each available service snapshot and its observation time.
  kind: product
  entities:
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
      place: mobile-app::device::city
---

# Read current city observations

## Trigger

The resident opens a city for which this phone has a live alert.

## Outcome

The city overview shows each available service snapshot and its observation time.

## Edge cases

- A successfully polled service with no slots is shown as empty.
- A service absent from the available snapshots is distinguished from a successfully polled empty service.
- A focused service from an alert or notification appears first.
- The app shares a one-minute snapshot cache with My alerts; a city push invalidates it.
