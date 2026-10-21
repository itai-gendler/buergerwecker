---
kind: primary
routes:
  main: Main
steps:
- text: The resident selects German or English in Settings.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::device::settings
- text: The app and widget use the selected language, and the device language is reported to the server.
  kind: product
  entities:
  - entity: push-device
    effect: changes
    facts:
    - Language
  - entity: resident
    effect: changes
    facts:
    - Preferred app language
  actor: resident
  contexts:
    main:
      place: mobile-app::device::settings
---

# Choose the app language on a registered phone

## Trigger

The resident selects German or English in Settings.

## Outcome

The app and widget use the selected language, and the device language is reported to the server.

## Edge cases

- The local language remains selected if reporting it to the server fails.
