---
kind: primary
routes:
  main: Main
steps:
- text: The operator opens administration.
  kind: actor
  entities: []
  actor: operator
  contexts:
    main:
      place: website::administration::status
- text: Current operational totals, dated observations and anomalies are shown.
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
  - entity: service-settings
    effect: reads
    facts:
    - Digest limit
    - Pressure limit
  actor: operator
  contexts:
    main:
      place: website::administration::status
---

# Read the service dashboard

## Trigger

The operator opens administration.

## Outcome

Current operational totals, dated observations and anomalies are shown.

## Edge cases

- Daily and monthly calendar totals are distinguished from rolling-24-hour usage that governs sending.
- Monthly configured mail quotas are display values rather than sending gates.
