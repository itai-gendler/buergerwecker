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
      place: website::subscription
  unattended: true
- text: The Product sends the appointment information and booking action, then records successful delivery for the saved search.
  kind: product
  entities:
  - entity: email-subscription
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
      place: website::subscription
---

# Deliver a matching email notification

## Trigger

An active search has eligible unseen matching slots and delivery allowance.

## Outcome

The Product sends the appointment information and booking action, then records successful delivery for the saved search.

## Edge cases

- The email lists the soonest 25 candidates by office and counts any remaining ones.
- The email repeats the saved selection and carries one booking link, plus links to manage or unsubscribe.
- The earliest 50 matching opportunities, including ones already reported, define each cycle’s notification horizon.
