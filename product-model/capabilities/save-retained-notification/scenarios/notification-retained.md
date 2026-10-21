---
kind: primary
routes:
  public: Public
  device: Device
steps:
- text: The app observes a slot or check-in push.
  kind: condition
  entities: []
  contexts:
    public:
      place: mobile-app::public::notifications
    device:
      place: mobile-app::device::notifications
  unattended: true
- text: The local list gains one unread entry, retaining original message time when supplied.
  kind: product
  entities:
  - entity: retained-notification
    effect: creates
    to: Unread
    facts:
    - Kind
    - Text
    - Received time
    - Destination
    - Read status
  contexts:
    public:
      place: mobile-app::public::notifications
    device:
      place: mobile-app::device::notifications
---

# Keep one observed notification

## Trigger

The app observes a slot or check-in push.

## Outcome

The local list gains one unread entry, retaining original message time when supplied.

## Edge cases

- A received message and a later copy of the same message remain one entry.
- A notification dismissed or replaced before the app observes it is not reconstructed.
