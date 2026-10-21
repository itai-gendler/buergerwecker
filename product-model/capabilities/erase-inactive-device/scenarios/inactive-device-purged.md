---
kind: edge
routes:
  main: Main
steps:
- text: A registration has had no activity for 30 days and holds neither a non-ended alert nor an alert ended within the last 30 days.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device
  unattended: true
- text: The inactive registration and any remaining ended alerts are erased.
  kind: product
  entities:
  - entity: push-device
    effect: removes
    from: Verified
  - entity: app-alert
    effect: removes
    from: Ended
    with: push-device
  contexts:
    main:
      place: mobile-app::device
---

# Erase a long-inactive registration

## Trigger

A registration has had no activity for 30 days and holds neither a non-ended alert nor an alert ended within the last 30 days.

## Outcome

The inactive registration and any remaining ended alerts are erased.
