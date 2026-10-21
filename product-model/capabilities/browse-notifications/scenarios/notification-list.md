---
kind: primary
routes:
  public: Public
  device: Device
steps:
- text: The resident opens Notifications.
  kind: actor
  entities: []
  actor: resident
  contexts:
    public:
      place: mobile-app::public::notifications
    device:
      place: mobile-app::device::notifications
- text: The current list is shown and its unread entries become read.
  kind: product
  entities:
  - entity: retained-notification
    effect: changes
    from: Unread
    to: Read
    facts:
    - Read status
  actor: resident
  contexts:
    public:
      place: mobile-app::public::notifications
    device:
      place: mobile-app::device::notifications
---

# Read recent notifications

## Trigger

The resident opens Notifications.

## Outcome

The current list is shown and its unread entries become read.

## Edge cases

- The list can be empty.
- Previously read entries remain readable.
