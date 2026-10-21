---
kind: edge
routes:
  main: Main
steps:
- text: The resident opens the city while the slot read fails.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::device::city
- text: The catalog and official booking action remain usable, with an appropriate retry or setup message.
  kind: product
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::device::city
---

# Keep catalog browsing after a snapshot failure

## Trigger

The resident opens the city while the slot read fails.

## Outcome

The catalog and official booking action remain usable, with an appropriate retry or setup message.

## Edge cases

- Snapshot reads have a shared per-device allowance of 60 per hour across the app and widget.
