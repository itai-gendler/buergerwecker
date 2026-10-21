---
kind: edge
routes:
  main: Main
steps:
- text: The resident chooses Keep looking during the grace period.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::device::alerts
- text: The paused search is active for a new term from now.
  kind: product
  entities:
  - entity: app-alert
    effect: changes
    from: Expired
    to: Active
    facts:
    - End date
    - Check-in sent
    - Active
  actor: resident
  contexts:
    main:
      place: mobile-app::device::alerts
---

# Resume an expired app search

## Trigger

The resident chooses Keep looking during the grace period.

## Outcome

The paused search is active for a new term from now.
