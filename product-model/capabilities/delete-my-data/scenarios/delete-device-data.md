---
kind: primary
routes:
  main: Main
steps:
- text: The resident confirms Delete my data.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::device::settings
- text: The Product removes the phone registration and its owned alerts, then clears widget data.
  kind: product
  entities:
  - entity: push-device
    effect: removes
    from: Verified
  - entity: app-alert
    effect: removes
    from: Active
    with: push-device
  actor: resident
  contexts:
    main:
      place: mobile-app::device::settings
- text: The Product removes retained notifications in this state.
  kind: product
  actor: resident
  entities:
  - entity: retained-notification
    effect: removes
    from: Unread
  contexts:
    main:
      place: mobile-app::device::settings
- text: The Product removes retained notifications in this state.
  kind: product
  actor: resident
  entities:
  - entity: retained-notification
    effect: removes
    from: Read
  contexts:
    main:
      place: mobile-app::device::settings
---

# Delete the phone and its alerts

## Trigger

The resident confirms Delete my data.

## Outcome

The phone registration and its alerts are removed; retained notifications and widget data are cleared and onboarding returns.

## Edge cases

- Expired and ended alerts owned by the device are removed too.
- An already absent or retired server registration permits local cleanup.
- A failed server deletion leaves the app showing the failure rather than claiming erasure.
