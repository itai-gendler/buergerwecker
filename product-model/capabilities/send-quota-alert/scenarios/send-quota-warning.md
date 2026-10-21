---
kind: primary
routes:
  main: Main
steps:
- text: Combined rolling mail usage reaches the warning line or a quota deferral occurs.
  kind: condition
  entities: []
  contexts:
    main:
      place: website::administration::status
  unattended: true
- text: The operator receives usage and deferral context to assess delivery capacity.
  kind: product
  entities:
  - entity: delivery-history
    effect: reads
    facts:
    - Volume
    - Deferrals
  - entity: operator
    effect: reads
    facts: []
  contexts:
    main:
      place: website::administration::status
---

# Report pressure on delivery capacity

## Trigger

Combined rolling mail usage reaches the warning line or a quota deferral occurs.

## Outcome

The operator receives usage and deferral context to assess delivery capacity.
