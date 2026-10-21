---
kind: edge
routes:
  main: Main
steps:
- text: The mail provider confirms delivery to an address with temporary failures and no suppression.
  kind: actor
  entities: []
  actor: mail-provider
  contexts:
    main:
      place: delivery-feedback
- text: The temporary-failure count is reset.
  kind: product
  entities:
  - entity: email-delivery
    effect: changes
    facts:
    - Temporary failures
  actor: mail-provider
  contexts:
    main:
      place: delivery-feedback
---

# Reset a temporary-failure run

## Trigger

The mail provider confirms delivery to an address with temporary failures and no suppression.

## Outcome

The temporary-failure count is reset.

## Edge cases

- Open and click events do not change subscriptions or track individual engagement.
- Unrecognized payloads are acknowledged and reflected as parsing problems in operator status.
