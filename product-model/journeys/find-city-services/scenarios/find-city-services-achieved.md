---
kind: primary
result: achieved
routes:
  web: Website
  mobile-public: Browse on phone
  mobile-device: Registered phone
steps:
- text: The resident chooses a city and office group.
  kind: actor
  actor: resident
  capability: browse-cities
  entities: &id001 []
  contexts:
    web:
      place: website::public::cities
    mobile-public:
      place: mobile-app::public::cities
    mobile-device:
      place: mobile-app::device::cities
- text: The Product opens the selected group’s services.
  kind: product
  actor: resident
  capability: browse-cities
  entities: *id001
  contexts:
    web:
      place: website::public::signup
    mobile-public:
      place: mobile-app::public::city
    mobile-device:
      place: mobile-app::device::city
- text: The resident reads the offered appointment types.
  kind: actor
  actor: resident
  capability: browse-appointment-types
  entities: *id001
  contexts:
    web:
      place: website::public::signup
    mobile-public:
      place: mobile-app::public::city
    mobile-device:
      place: mobile-app::device::city
---

# Find the selected city’s services

## Trigger

The resident selects a city group.

## Outcome

The group’s offered appointment types are shown.
