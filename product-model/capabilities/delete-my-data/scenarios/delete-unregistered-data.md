---
kind: primary
routes:
  main: Main
steps:
- text: The resident confirms Delete my data before registering.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::public::settings
- text: The app returns to onboarding with the chosen language retained.
  kind: product
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::public::settings
---

# Clear local data without a registration

## Trigger

The resident confirms Delete my data before registering.

## Outcome

The app returns to onboarding with the chosen language retained.
