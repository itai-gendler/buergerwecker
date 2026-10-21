---
kind: primary
routes:
  web-public: Web Public
  web-link: Web Link
  mobile-public: Mobile Public
  mobile-device: Mobile Device
steps:
- text: The resident follows Book on the city’s site or a notification booking link.
  kind: actor
  entities: []
  actor: resident
  contexts:
    web-public:
      place: website::public
    web-link:
      place: website::subscription
    mobile-public:
      place: mobile-app::public::city
    mobile-device:
      place: mobile-app::device::city
- text: The official booking start page opens; date and time in the notification are guidance rather than a reserved appointment.
  kind: product
  entities: []
  actor: resident
  contexts:
    web-public:
      place: website::public
    web-link:
      place: website::subscription
    mobile-public:
      place: mobile-app::public::city
    mobile-device:
      place: mobile-app::device::city
---

# Continue on the city’s website

## Trigger

The resident follows Book on the city’s site or a notification booking link.

## Outcome

The official booking start page opens; date and time in the notification are guidance rather than a reserved appointment.

## Edge cases

- The app uses the system browser.
- A removed city or old slot-specific link shows an expired-link result.
- A special-category email uses a subscription-specific booking link.
- Where the city requires a personal Termin-Code, the resident supplies it to the city.
