---
kind: primary
routes:
  public: Public
  device: Device
steps:
- text: The resident taps a retained slot entry.
  kind: actor
  entities: []
  actor: resident
  contexts:
    public:
      place: mobile-app::public::notifications
    device:
      place: mobile-app::device::notifications
- text: The app opens the city overview focused on the alert’s service when it is still known, rather than opening the old booking link.
  kind: product
  entities:
  - entity: retained-notification
    effect: reads
    facts:
    - Kind
    - Destination
  actor: resident
  contexts:
    public:
      place: mobile-app::public::notifications
    device:
      place: mobile-app::device::notifications
---

# Open current availability from history

## Trigger

The resident taps a retained slot entry.

## Outcome

The app opens the city overview focused on the alert’s service when it is still known, rather than opening the old booking link.

## Edge cases

- If neither the entry nor a current alert identifies the city, the app opens My alerts.
