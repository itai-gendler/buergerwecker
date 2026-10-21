---
kind: primary
result: achieved
routes:
  main: Main
steps:
- text: The resident opens the check-in notification.
  kind: actor
  entities:
  - entity: retained-notification
    effect: reads
    facts:
    - Kind
    - Destination
  actor: resident
  contexts:
    main:
      place: mobile-app::device::notifications
  capability: follow-retained-notification
- text: The Product opens the still-looking question in My alerts.
  kind: product
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::device::alerts
  capability: follow-retained-notification
- text: The resident chooses Yes, keep looking for the app alert.
  kind: actor
  entities:
  - entity: app-alert
    effect: changes
    facts:
    - End date
    - Check-in sent
  actor: resident
  contexts:
    main:
      place: mobile-app::device::alerts
  capability: renew-subscription
---

# Answer a check-in with Keep looking

## Trigger

The resident follows a retained still-looking notification.

## Outcome

The selected app alert has a new term and its check-in is answered.
