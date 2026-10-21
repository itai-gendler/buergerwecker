---
kind: primary
result: achieved
routes:
  main: Main
steps:
- text: The resident follows the slot notification.
  kind: actor
  entities:
  - entity: retained-notification
    effect: reads
    facts:
    - Kind
    - Destination
  actor: resident
  contexts:
    main:
      place: mobile-app::device::notifications
  capability: follow-retained-notification
- text: The Product opens the focused city overview.
  kind: product
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::device::city
  capability: follow-retained-notification
- text: The resident reads the current free slots and last-check time.
  kind: actor
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
  capability: view-city-availability
---

# Open a retained slot notification in the city overview

## Trigger

The resident follows a retained slot notification.

## Outcome

The current city observations are shown for the service referenced by the retained alert.
