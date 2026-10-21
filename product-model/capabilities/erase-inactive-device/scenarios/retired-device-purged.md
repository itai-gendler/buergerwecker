---
kind: primary
routes:
  main: Main
steps:
- text: Housekeeping finds a device retired more than 30 days ago.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device
  unattended: true
- text: The retained registration and any remaining owned alerts are erased.
  kind: product
  entities:
  - entity: push-device
    effect: removes
    from: Retired
  - entity: app-alert
    effect: removes
    from: Ended
    with: push-device
  contexts:
    main:
      place: mobile-app::device
---

# Erase a retired registration

## Trigger

Housekeeping finds a device retired more than 30 days ago.

## Outcome

The retained registration and any remaining owned alerts are erased.
