---
kind: primary
routes:
  main: Main
steps:
- text: A watched city is due for polling.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device::city
  unattended: true
- text: The Product keeps deduplicated free slots from the complete service poll, limited to the soonest 100 per service for app browsing.
  kind: product
  entities:
  - entity: free-slot
    effect: creates
    facts:
    - City and office group
    - Appointment type
    - Office
    - Date
    - Time
    - Last checked
  contexts:
    main:
      place: mobile-app::device::city
---

# Keep newly observed free appointments

## Trigger

A watched city is due for polling.

## Outcome

The Product keeps deduplicated free slots from the complete service poll, limited to the soonest 100 per service for app browsing.

## Edge cases

- The total available count includes opportunities beyond the retained 100.
- Only watched services are polled; opening the app causes no additional city-site poll.
- Normal catalog polling intervals are one to three minutes, configured per city.
