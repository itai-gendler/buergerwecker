---
kind: primary
routes:
  main: Main
steps:
- text: The mail provider reports a hard bounce for an address.
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

# Apply a permanent delivery failure

## Trigger

The mail provider reports a hard bounce for an address.

## Outcome

Email delivery is blocked and active email subscriptions at that address are ended.
