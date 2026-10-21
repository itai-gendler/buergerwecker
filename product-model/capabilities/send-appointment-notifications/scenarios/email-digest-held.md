---
kind: edge
routes:
  main: Main
steps:
- text: New candidates exist but this search has reached its rolling-24-hour digest limit.
  kind: condition
  entities:
  - entity: email-subscription
    effect: reads
    facts:
    - Last notified
  contexts:
    main:
      place: website::subscription
  unattended: true
- text: Nothing is marked delivered or seen; the next eligible cycle checks which matching appointments are still open.
  kind: product
  entities: []
  contexts:
    main:
      place: website::subscription
---

# Hold an email notification at the rolling limit

## Trigger

New candidates exist but this search has reached its rolling-24-hour digest limit.

## Outcome

Nothing is marked delivered or seen; the next eligible cycle checks which matching appointments are still open.
