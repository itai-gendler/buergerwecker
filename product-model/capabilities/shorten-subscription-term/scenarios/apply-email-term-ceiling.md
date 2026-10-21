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
      place: website::subscription
  unattended: true
- text: The end date is pulled in to the applicable term ceiling.
  kind: product
  entities:
  - entity: email-subscription
    effect: changes
    facts:
    - End date
  contexts:
    main:
      place: website::subscription
---

# Shorten an email subscription term to its ceiling

## Trigger

Housekeeping finds an end date later than now plus the applicable configured term.

## Outcome

The end date is pulled in to the applicable term ceiling.
