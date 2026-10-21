---
kind: edge
routes:
  main: Main
steps:
- text: The resident follows a confirmation link after its term ended.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
- text: An unconfirmed request points to sign-up again. An already confirmed request offers Keep looking.
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

# Handle a confirmation after the term

## Trigger

The resident follows a confirmation link after its term ended.

## Outcome

An unconfirmed request points to sign-up again. An already confirmed request offers Keep looking.

## Edge cases

- A removed request is not found.
