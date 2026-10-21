---
kind: edge
routes:
  main: Main
steps:
- text: The resident opens the app while the mobile service is disabled.
  kind: actor
  actor: resident
  entities: []
  contexts:
    main:
      place: mobile-app::public::setup
- text: The app shows its unavailable view with a retry action.
  kind: product
  actor: resident
  entities: []
  contexts:
    main:
      place: mobile-app::public::setup
---

# Show mobile-service unavailability

## Trigger

The resident opens the app while the mobile service is disabled.

## Outcome

The app shows its unavailable view with a retry action.
