---
kind: validation
routes:
  web: Web
  mobile: Mobile
steps:
- text: The resident saves invalid preferences or a selection exceeding current city capacity.
  kind: actor
  entities: []
  actor: resident
  contexts:
    web:
      place: website::subscription::subscription
    mobile:
      place: mobile-app::device::form
- text: The error is shown and the previous filter remains in force.
  kind: product
  entities: []
  actor: resident
  contexts:
    web:
      place: website::subscription::subscription
    mobile:
      place: mobile-app::device::form
---

# Keep the existing filter after refusal

## Trigger

The resident saves invalid preferences or a selection exceeding current city capacity.

## Outcome

The error is shown and the previous filter remains in force.
