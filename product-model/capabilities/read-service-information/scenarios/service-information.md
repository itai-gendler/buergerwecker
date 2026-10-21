---
kind: primary
routes:
  web: Web
  mobile-public: Mobile Public
  mobile-device: Mobile Device
steps:
- text: The resident opens the service information or a legal-information link.
  kind: actor
  entities: []
  actor: resident
  contexts:
    web:
      place: website::public::information
    mobile-public:
      place: mobile-app::public::settings
    mobile-device:
      place: mobile-app::device::settings
- text: The FAQ, privacy notice or imprint is available in the selected language.
  kind: product
  entities: []
  actor: resident
  contexts:
    web:
      place: website::public::information
    mobile-public:
      place: mobile-app::public::settings
    mobile-device:
      place: mobile-app::device::settings
---

# Read how the service works

## Trigger

The resident opens the service information or a legal-information link.

## Outcome

The FAQ, privacy notice or imprint is available in the selected language.

## Edge cases

- The FAQ explains manual booking, limited notification frequency and the still-looking check-in.
