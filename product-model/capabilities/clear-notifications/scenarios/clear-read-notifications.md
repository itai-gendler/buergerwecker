---
kind: primary
routes:
  public: Public
  device: Device
steps:
- text: The resident selects Clear list after opening Notifications.
  kind: actor
  entities: []
  actor: resident
  contexts:
    public:
      place: mobile-app::public::notifications
    device:
      place: mobile-app::device::notifications
- text: The locally retained entries are removed and the unread count is cleared.
  kind: product
  entities:
  - entity: retained-notification
    effect: removes
    from: Read
  actor: resident
  contexts:
    public:
      place: mobile-app::public::notifications
    device:
      place: mobile-app::device::notifications
---

# Clear the displayed list

## Trigger

The resident selects Clear list after opening Notifications.

## Outcome

The locally retained entries are removed and the unread count is cleared.

## Edge cases

- Remembered notification identities prevent an already-cleared system copy from immediately reappearing.
