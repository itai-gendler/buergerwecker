---
kind: edge
routes:
  main: Main
steps:
- text: The resident enters a city or office-group name.
  kind: actor
  actor: resident
  entities: []
  contexts:
    main:
      place: mobile-app::public::cities
- text: The matching city groups are shown, or the app reports no matching city.
  kind: product
  actor: resident
  entities: []
  contexts:
    main:
      place: mobile-app::public::cities
---

# Find a city or office group

## Trigger

The resident enters a city or office-group name.

## Outcome

The matching city groups are shown, or the app reports no matching city.
