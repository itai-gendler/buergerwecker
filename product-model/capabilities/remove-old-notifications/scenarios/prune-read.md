---
kind: edge
routes:
  public: Public
  device: Device
steps:
- text: The local list is loaded or a notification is recorded.
  kind: condition
  entities: []
  contexts:
    public:
      place: mobile-app::public::notifications
    device:
      place: mobile-app::device::notifications
  unattended: true
- text: Entries beyond the age or count limit are removed.
  kind: product
  entities:
  - entity: retained-notification
    effect: removes
    from: Read
  contexts:
    public:
      place: mobile-app::public::notifications
    device:
      place: mobile-app::device::notifications
---

# Remove retained read entries

## Trigger

The local list is loaded or a notification is recorded.

## Outcome

Entries beyond the age or count limit are removed.
