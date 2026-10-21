---
kind: edge
routes:
  main: Main
steps:
- text: An active sensitive-service email search has new eligible matching appointments.
  kind: condition
  entities: []
  contexts:
    main:
      place: website::subscription
  unattended: true
- text: The email carries dates, times and its booking action while omitting service and office names.
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
  contexts:
    main:
      place: website::subscription
---

# Deliver a sensitive-service email

## Trigger

An active sensitive-service email search has new eligible matching appointments.

## Outcome

The email carries dates, times and its booking action while omitting service and office names.
