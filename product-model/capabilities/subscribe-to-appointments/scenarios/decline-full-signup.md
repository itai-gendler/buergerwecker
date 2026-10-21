---
kind: edge
routes:
  web: Web
  mobile: Mobile
steps:
- text: The resident submits a new selection when its applicable capacity is full.
  kind: actor
  entities: []
  actor: resident
  contexts:
    web:
      place: website::public::signup
    mobile:
      place: mobile-app::device::form
- text: The form explains the waitlist or device limit; no new request is saved.
  kind: product
  entities: []
  actor: resident
  contexts:
    web:
      place: website::public::signup
    mobile:
      place: mobile-app::device::form
---

# Keep a full waitlist unchanged

## Trigger

The resident submits a new selection when its applicable capacity is full.

## Outcome

The form explains the waitlist or device limit; no new request is saved.
