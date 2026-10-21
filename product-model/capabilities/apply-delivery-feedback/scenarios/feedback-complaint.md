---
kind: edge
routes:
  main: Main
steps:
- text: The mail provider reports a complaint for an address.
  kind: actor
  entities: []
  actor: mail-provider
  contexts:
    main:
      place: delivery-feedback
- text: Email delivery is blocked and active email subscriptions at that address are ended.
  kind: product
  entities:
  - entity: email-delivery
    effect: changes
    from: Reachable
    to: Blocked
    facts:
    - Block reason
    - Blocked since
  - entity: email-subscription
    effect: changes
    from: Active
    to: Ended
    facts: []
  actor: mail-provider
  contexts:
    main:
      place: delivery-feedback
---

# Apply a spam complaint

## Trigger

The mail provider reports a complaint for an address.

## Outcome

Email delivery is blocked and active email subscriptions at that address are ended.
