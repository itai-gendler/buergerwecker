---
kind: primary
routes:
  main: Main
steps:
- text: Daily housekeeping finds no backup timestamp within 48 hours.
  kind: condition
  entities: []
  contexts:
    main:
      place: website::administration::status
  unattended: true
- text: The operator receives a stale-backup notification.
  kind: product
  entities:
  - entity: polling-history
    effect: reads
    facts:
    - Maintenance
  - entity: operator
    effect: reads
    facts: []
  contexts:
    main:
      place: website::administration::status
---

# Report a missing recent backup

## Trigger

Daily housekeeping finds no backup timestamp within 48 hours.

## Outcome

The operator receives a stale-backup notification.
