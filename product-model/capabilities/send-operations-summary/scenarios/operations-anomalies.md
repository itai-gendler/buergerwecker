---
kind: primary
routes:
  main: Main
steps:
- text: Daily housekeeping finds operational anomalies.
  kind: condition
  entities: []
  contexts:
    main:
      place: website::administration::status
  unattended: true
- text: The operator receives a summary with current anomalies and service figures.
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

# Report conditions needing attention

## Trigger

Daily housekeeping finds operational anomalies.

## Outcome

The operator receives a summary with current anomalies and service figures.

## Edge cases

- Any successful summary restarts the weekly all-clear clock.
- A quiet day within that week sends no summary.
