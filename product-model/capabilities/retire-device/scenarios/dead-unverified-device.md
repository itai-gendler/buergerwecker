---
kind: edge
routes:
  main: Main
steps:
- text: The relay establishes that an unverified setup destination is dead with the same supporting delivery evidence.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device
  unattended: true
- text: The unverified device is retired.
  kind: product
  entities:
  - entity: push-device
    effect: changes
    from: Unverified
    to: Retired
    facts: []
  contexts:
    main:
      place: mobile-app::device
---

# Retire an unusable setup destination

## Trigger

The relay establishes that an unverified setup destination is dead with the same supporting delivery evidence.

## Outcome

The unverified device is retired.
