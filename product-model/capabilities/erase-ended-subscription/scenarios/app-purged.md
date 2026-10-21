---
kind: primary
routes:
  main: Main
steps:
- text: Housekeeping finds a saved search ended more than 30 days ago.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device
  unattended: true
- text: The retained search and its dependent delivery records are removed.
  kind: product
  entities:
  - entity: app-alert
    effect: removes
    from: Ended
  contexts:
    main:
      place: mobile-app::device
---

# Erase retained ended app data

## Trigger

Housekeeping finds a saved search ended more than 30 days ago.

## Outcome

The retained search and its dependent delivery records are removed.
