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
      place: mobile-app::public::settings
- text: The app saves the language and reloads localized catalog content.
  kind: product
  entities:
  - entity: resident
    effect: changes
    facts:
    - Preferred app language
  actor: resident
  contexts:
    main:
      place: mobile-app::public::settings
---

# Choose the app language before registration

## Trigger

The resident selects German or English in Settings.

## Outcome

The app saves the language and reloads localized catalog content.
