---
kind: primary
routes:
  web: Web
  mobile-public: Mobile Public
  mobile-device: Mobile Device
steps:
- text: The resident opens the city picker.
  kind: actor
  entities: []
  actor: resident
  contexts:
    web:
      place: website::public::cities
    mobile-public:
      place: mobile-app::public::cities
    mobile-device:
      place: mobile-app::device::cities
- text: The supported city groups are shown; selecting a group opens its services.
  kind: product
  entities: []
  actor: resident
  contexts:
    web:
      place: website::public::cities
    mobile-public:
      place: mobile-app::public::cities
    mobile-device:
      place: mobile-app::device::cities
---

# Choose a city

## Trigger

The resident opens the city picker.

## Outcome

The supported city groups are shown; selecting a group opens its services.

## Edge cases

- An unknown web city displays the picker with a not-found result.
- A city whose catalog cannot be loaded is omitted.
