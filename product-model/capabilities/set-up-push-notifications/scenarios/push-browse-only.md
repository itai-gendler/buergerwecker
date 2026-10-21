---
kind: edge
routes:
  main: Main
steps:
- text: The resident chooses to browse first or declines notification permission.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::public::setup
- text: Cities remain available; creating an alert still needs completed notification setup.
  kind: product
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::public::setup
---

# Browse without notification permission

## Trigger

The resident chooses to browse first or declines notification permission.

## Outcome

Cities remain available; creating an alert still needs completed notification setup.
