---
kind: primary
routes:
  main: Main
steps:
- text: The saved search reaches its end date.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device::alerts
  unattended: true
- text: The search is expired and no longer participates in appointment delivery.
  kind: product
  entities:
  - entity: app-alert
    effect: changes
    from: Active
    to: Expired
    facts:
    - Active
  contexts:
    main:
      place: mobile-app::device::alerts
---

# Pause the app search at its deadline

## Trigger

The saved search reaches its end date.

## Outcome

The search is expired and no longer participates in appointment delivery.
