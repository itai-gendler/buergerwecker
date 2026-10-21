---
kind: edge
routes:
  main: Main
steps:
- text: The resident taps a slot push or its foreground banner.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::device
- text: The app opens the supplied booking link in the system browser and, when supplied, the city overview focused on the known service.
  kind: product
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::device
---

# Follow a received slot push

## Trigger

The resident taps a slot push or its foreground banner.

## Outcome

The app opens the supplied booking link in the system browser and, when supplied, the city overview focused on the known service.
