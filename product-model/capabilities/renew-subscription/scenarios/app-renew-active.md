---
kind: primary
routes:
  main: Main
steps:
- text: The resident chooses Yes, keep looking.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::device::alerts
- text: A new term begins now and the next term can receive its own check-in.
  kind: product
  entities:
  - entity: app-alert
    effect: changes
    facts:
    - End date
    - Check-in sent
  actor: resident
  contexts:
    main:
      place: mobile-app::device::alerts
---

# Extend an active app search

## Trigger

The resident chooses Yes, keep looking.

## Outcome

A new term begins now and the next term can receive its own check-in.
