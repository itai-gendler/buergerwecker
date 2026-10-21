---
kind: primary
routes:
  web: Web
  mobile-public: Mobile Public
  mobile-device: Mobile Device
steps:
- text: The resident selects an office group.
  kind: actor
  entities: []
  actor: resident
  contexts:
    web:
      place: website::public::signup
    mobile-public:
      place: mobile-app::public::city
    mobile-device:
      place: mobile-app::device::city
- text: The offered services, office names and city notes are available.
  kind: product
  entities: []
  actor: resident
  contexts:
    web:
      place: website::public::signup
    mobile-public:
      place: mobile-app::public::city
    mobile-device:
      place: mobile-app::device::city
---

# Read available services

## Trigger

The resident selects an office group.

## Outcome

The offered services, office names and city notes are available.

## Edge cases

- English labels fall back individually to German without dropping services.
- Known service-to-office coverage narrows offices in the web sign-up and mobile form; unknown coverage shows the catalog offices.
