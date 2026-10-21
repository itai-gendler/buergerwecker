---
kind: edge
routes:
  main: Main
steps:
- text: An unverified registration is over a day old, has no recent setup request and has never held any subscription row.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device
  unattended: true
- text: The unverified registration is erased; a later launch starts setup again.
  kind: product
  entities:
  - entity: push-device
    effect: removes
    from: Unverified
  contexts:
    main:
      place: mobile-app::device
---

# Erase abandoned notification setup

## Trigger

An unverified registration is over a day old, has no recent setup request and has never held any subscription row.

## Outcome

The unverified registration is erased; a later launch starts setup again.
