---
kind: primary
routes:
  main: Main
steps:
- text: The resident accepts the notification request.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::public::setup
- text: The Product registers the push device and requests a setup push.
  kind: product
  entities:
  - entity: push-device
    effect: creates
    to: Unverified
    facts:
    - Platform
    - Language
    - Push destination
    - Verification
    - Last activity
  actor: resident
  contexts:
    main:
      place: mobile-app::public::setup
- text: The Product acknowledges the received setup code and verifies the push device.
  kind: product
  entities:
  - entity: push-device
    effect: changes
    from: Unverified
    to: Verified
    facts:
    - Verification
  actor: resident
  contexts:
    main:
      place: mobile-app::public::setup
---

# Complete notification setup

## Trigger

The resident chooses to enable notifications.

## Outcome

The device is verified and the app can load its alerts.

## Edge cases

- If immediate delivery fails, the background verification sweep can send the setup push later.
- A repeated successful verification remains successful.
