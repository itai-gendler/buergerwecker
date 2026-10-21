---
kind: primary
routes:
  main: Main
steps:
- text: The resident chooses Yes, keep looking.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
- text: A new term begins now and the next term can receive its own check-in.
  kind: product
  entities:
  - entity: email-subscription
    effect: changes
    facts:
    - End date
    - Check-in sent
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
---

# Extend an active email search

## Trigger

The resident chooses Yes, keep looking.

## Outcome

A new term begins now and the next term can receive its own check-in.
