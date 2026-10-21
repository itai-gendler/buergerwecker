---
kind: primary
routes:
  main: Main
steps:
- text: A dead-destination response has supporting successful delivery on that platform since the first such response.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device
  unattended: true
- text: The device is retired and its active alerts are ended.
  kind: product
  entities:
  - entity: push-device
    effect: changes
    from: Verified
    to: Retired
    facts: []
  - entity: app-alert
    effect: changes
    from: Active
    to: Ended
    facts:
    - Active
  contexts:
    main:
      place: mobile-app::device
---

# End delivery to a dead destination

## Trigger

A dead-destination response has supporting successful delivery on that platform since the first such response.

## Outcome

The device is retired and its active alerts are ended.

## Edge cases

- The destination must still be the one to which delivery failed.
- Expired alerts are also ended.
