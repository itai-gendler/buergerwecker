---
kind: primary
routes:
  main: Main
steps:
- text: An active search has eligible unseen matching slots and delivery allowance.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device
  unattended: true
- text: The Product sends the appointment information and booking action, then records successful delivery for the saved search.
  kind: product
  entities:
  - entity: app-alert
    effect: changes
    facts:
    - Last notified
    - Cadence
  - entity: free-slot
    effect: reads
    facts:
    - Date
    - Time
    - Office
    - Appointment type
  contexts:
    main:
      place: mobile-app::device
---

# Deliver a matching push notification

## Trigger

An active search has eligible unseen matching slots and delivery allowance.

## Outcome

The Product sends the appointment information and booking action, then records successful delivery for the saved search.

## Edge cases

- The push lists up to three offices, soonest first, with up to three times each, and counts the rest as more.
- The push opens the city's booking start page; while the app is open it appears as an in-app banner.
- The earliest 50 matching opportunities, including ones already reported, define each cycle’s notification horizon.
