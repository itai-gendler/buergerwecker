---
kind: edge
routes:
  email: Email
  app: App
steps:
- text: A day-granularity city offers a strictly earlier time at the same office and service on an already-reported day.
  kind: condition
  entities: []
  contexts:
    email:
      place: website::subscription
    app:
      place: mobile-app::device
  unattended: true
- text: The earlier opportunity qualifies as new and may be delivered subject to cadence and quota.
  kind: product
  entities:
  - entity: free-slot
    effect: reads
    facts:
    - Date
    - Time
    - Office
    - Appointment type
  contexts:
    email:
      place: website::subscription
    app:
      place: mobile-app::device
---

# Notify about an earlier opening on a reported day

## Trigger

A day-granularity city offers a strictly earlier time at the same office and service on an already-reported day.

## Outcome

The earlier opportunity qualifies as new and may be delivered subject to cadence and quota.
