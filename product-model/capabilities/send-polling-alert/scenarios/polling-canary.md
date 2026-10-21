---
kind: primary
routes:
  main: Main
steps:
- text: The configured duration threshold is crossed during the canary checking window.
  kind: condition
  entities: []
  contexts:
    main:
      place: website::administration::status
  unattended: true
- text: The operator receives the city or vendor problem with its observed duration.
  kind: product
  entities:
  - entity: polling-history
    effect: reads
    facts:
    - Latest poll
    - Failures
  - entity: operator
    effect: reads
    facts: []
  contexts:
    main:
      place: website::administration::status
---

# Report a sustained polling anomaly

## Trigger

The configured duration threshold is crossed during the canary checking window.

## Outcome

The operator receives the city or vendor problem with its observed duration.

## Edge cases

- One city with no available slots alone does not trigger the vendor-empty alert.
- Each named canary alert is normally limited to once per day.
- The separate poller failure alert reports repeated cycle errors.
