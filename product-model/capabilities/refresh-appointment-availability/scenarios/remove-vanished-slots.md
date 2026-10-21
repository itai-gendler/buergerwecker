---
kind: edge
routes:
  main: Main
steps:
- text: A complete service poll replaces its previous result.
  kind: condition
  unattended: true
  entities: []
  contexts:
    main:
      place: mobile-app::device::city
- text: The Product removes free slots absent from the new result.
  kind: product
  entities:
  - entity: free-slot
    effect: removes
  contexts:
    main:
      place: mobile-app::device::city
---

# Remove opportunities absent from a complete poll

## Trigger

A complete service poll no longer contains previously observed appointments.

## Outcome

Those free slots are removed from current server observations.
