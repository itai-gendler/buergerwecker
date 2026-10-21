---
kind: edge
routes:
  main: Main
steps:
- text: At least one plan for a service fails.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device::city
  unattended: true
- text: The previous observation remains with its original last-checked time; an outage is not presented as a new empty result.
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
  contexts:
    main:
      place: mobile-app::device::city
---

# Keep the previous complete result

## Trigger

At least one plan for a service fails.

## Outcome

The previous observation remains with its original last-checked time; an outage is not presented as a new empty result.
