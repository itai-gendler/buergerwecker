---
kind: primary
routes:
  main: Main
steps:
- text: Housekeeping finds an end date later than now plus the applicable configured term.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device
  unattended: true
- text: The end date is pulled in to the applicable term ceiling.
  kind: product
  entities:
  - entity: app-alert
    effect: changes
    facts:
    - End date
  contexts:
    main:
      place: mobile-app::device
---

# Shorten an app alert term to its ceiling

## Trigger

Housekeeping finds an end date later than now plus the applicable configured term.

## Outcome

The end date is pulled in to the applicable term ceiling.
