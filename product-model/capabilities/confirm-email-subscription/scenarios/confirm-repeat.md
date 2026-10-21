---
kind: edge
routes:
  main: Main
steps:
- text: The resident follows the confirmation link again.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
- text: The existing confirmation is shown without restarting the term.
  kind: product
  entities:
  - entity: email-subscription
    effect: reads
    facts:
    - End date
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
---

# Reopen an active confirmation

## Trigger

The resident follows the confirmation link again.

## Outcome

The existing confirmation is shown without restarting the term.
