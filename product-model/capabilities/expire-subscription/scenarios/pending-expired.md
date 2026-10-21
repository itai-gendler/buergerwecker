---
kind: edge
routes:
  main: Main
steps:
- text: An unconfirmed email request reaches the end of its saved term.
  kind: condition
  entities: []
  contexts:
    main:
      place: website::subscription
  unattended: true
- text: The email subscription is expired; its confirmation page directs the resident to sign up again.
  kind: product
  entities:
  - entity: email-subscription
    effect: changes
    from: Pending
    to: Expired
    facts: []
  - entity: resident
    effect: reads
    facts: []
  contexts:
    main:
      place: website::subscription
---

# Let an unconfirmed sign-up expire

## Trigger

An unconfirmed email request reaches the end of its saved term.

## Outcome

The email subscription is expired; its confirmation page directs the resident to sign up again.
