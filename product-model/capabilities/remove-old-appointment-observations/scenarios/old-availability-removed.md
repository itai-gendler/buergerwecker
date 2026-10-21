---
kind: primary
routes:
  main: Main
steps:
- text: Housekeeping finds a snapshot more than 24 hours old.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device::city
  unattended: true
- text: Its retained free slots are removed from the server’s overview data.
  kind: product
  entities:
  - entity: free-slot
    effect: removes
  contexts:
    main:
      place: mobile-app::device::city
---

# Remove stale server observations

## Trigger

Housekeeping finds a snapshot more than 24 hours old.

## Outcome

Its retained free slots are removed from the server’s overview data.
