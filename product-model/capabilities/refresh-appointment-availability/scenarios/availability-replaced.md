---
kind: edge
routes:
  main: Main
steps:
- text: A later complete service poll succeeds.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device::city
  unattended: true
- text: Previously observed free slots present in the new result are refreshed with the new last-checked time.
  kind: product
  entities:
  - entity: free-slot
    effect: changes
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

# Replace a previous observation

## Trigger

A later complete service poll succeeds.

## Outcome

Previously observed free slots present in the new result are refreshed with the new last-checked time.
