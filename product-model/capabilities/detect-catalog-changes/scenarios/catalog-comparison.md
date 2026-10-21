---
kind: primary
routes:
  main: Main
steps:
- text: The configured daily catalog comparison runs.
  kind: condition
  entities: []
  contexts:
    main:
      place: website::administration::status
  unattended: true
- text: Operator status records watched service or office identifiers absent upstream; packaged catalogs remain the selected service source.
  kind: product
  entities:
  - entity: polling-history
    effect: reads
    facts:
    - Catalog differences
  - entity: operator
    effect: reads
    facts: []
  contexts:
    main:
      place: website::administration::status
---

# Report missing watched catalog entries

## Trigger

The configured daily catalog comparison runs.

## Outcome

Operator status records watched service or office identifiers absent upstream; packaged catalogs remain the selected service source.

## Edge cases

- A failed comparison preserves the prior result for that city.
- Excluded services are not reported as missing watched services.
