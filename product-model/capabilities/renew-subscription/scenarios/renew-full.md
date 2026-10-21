---
kind: edge
routes:
  web: Web
  mobile: Mobile
steps:
- text: The resident asks to keep looking when current city admission is full.
  kind: actor
  entities: []
  actor: resident
  contexts:
    web:
      place: website::subscription::subscription
    mobile:
      place: mobile-app::device::alerts
- text: The current term is unchanged; no additional term is promised.
  kind: product
  entities: []
  actor: resident
  contexts:
    web:
      place: website::subscription::subscription
    mobile:
      place: mobile-app::device::alerts
---

# Preserve the term when renewal is declined

## Trigger

The resident asks to keep looking when current city admission is full.

## Outcome

The current term is unchanged; no additional term is promised.

## Edge cases

- An ended or purged request is not renewable.
