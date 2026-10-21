---
kind: edge
routes:
  main: Main
steps:
- text: The resident stops an expired search.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::device::alerts
- text: The search is ended rather than available for renewal.
  kind: product
  entities:
  - entity: app-alert
    effect: changes
    from: Expired
    to: Ended
    facts:
    - Active
  actor: resident
  contexts:
    main:
      place: mobile-app::device::alerts
---

# Stop an expired search

## Trigger

The resident stops an expired search.

## Outcome

The search is ended rather than available for renewal.
