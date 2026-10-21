---
kind: edge
routes:
  main: Main
steps:
- text: No anomalies are present and a week has passed without an operations summary.
  kind: condition
  entities: []
  contexts:
    main:
      place: website::administration::status
  unattended: true
- text: The operator receives an all-clear with service figures.
  kind: product
  entities:
  - entity: delivery-history
    effect: reads
    facts:
    - Volume
    - Deferrals
    - Subscriber holds
    - Feedback
  - entity: polling-history
    effect: reads
    facts:
    - Latest poll
    - Failures
    - Catalog differences
    - Maintenance
  - entity: operator
    effect: reads
    facts: []
  contexts:
    main:
      place: website::administration::status
---

# Send the weekly all-clear

## Trigger

No anomalies are present and a week has passed without an operations summary.

## Outcome

The operator receives an all-clear with service figures.
