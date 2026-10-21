---
kind: edge
routes:
  public: Public
  device: Device
steps:
- text: The resident taps a retained check-in entry.
  kind: actor
  entities: []
  actor: resident
  contexts:
    public:
      place: mobile-app::public::notifications
    device:
      place: mobile-app::device::notifications
- text: My alerts opens with the matching alert’s Yes, keep looking and No, I have got one question.
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

# Open the still-looking question

## Trigger

The resident taps a retained check-in entry.

## Outcome

My alerts opens with the matching alert’s Yes, keep looking and No, I have got one question.

## Edge cases

- If the alert no longer exists, the current list opens without a question.
