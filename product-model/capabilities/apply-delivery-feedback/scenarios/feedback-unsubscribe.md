---
kind: edge
routes:
  main: Main
steps:
- text: The mail provider reports an unsubscribe.
  kind: actor
  entities: []
  actor: mail-provider
  contexts:
    main:
      place: delivery-feedback
- text: Active email subscriptions for that address are ended; the address is not newly suppressed.
  kind: product
  entities:
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

# Apply an address-wide unsubscribe

## Trigger

The mail provider reports an unsubscribe.

## Outcome

Active email subscriptions for that address are ended; the address is not newly suppressed.
