---
kind: edge
routes:
  main: Main
steps:
- text: The mail provider reports the temporary failure that reaches the configured threshold.
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
    - Temporary failures
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

# Stop after repeated temporary failures

## Trigger

The mail provider reports the temporary failure that reaches the configured threshold.

## Outcome

Email delivery is blocked and active email subscriptions at that address are ended.
