---
kind: validation
routes:
  web: Web
  mobile: Mobile
steps:
- text: The resident submits an unknown service or office, or a time window whose start is after its end.
  kind: actor
  entities: []
  actor: resident
  contexts:
    web:
      place: website::public::signup
    mobile:
      place: mobile-app::device::form
- text: The form reports the invalid input and saves no request.
  kind: product
  entities: []
  actor: resident
  contexts:
    web:
      place: website::public::signup
    mobile:
      place: mobile-app::device::form
---

# Decline invalid appointment preferences

## Trigger

The resident submits an unknown service or office, or a time window whose start is after its end.

## Outcome

The form reports the invalid input and saves no request.

## Edge cases

- The web form also rejects an invalid email address.
- The mobile form requires at least one weekday and at least one office when all offices is not selected.
- Special-category web selection requires explicit separate consent.
