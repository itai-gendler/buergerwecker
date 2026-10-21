---
kind: edge
routes:
  main: Main
steps:
- text: The mail provider reports a temporary bounce below the suppression threshold.
  kind: actor
  entities: []
  actor: mail-provider
  contexts:
    main:
      place: delivery-feedback
- text: The temporary-failure count increases while the address remains mailable.
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

# Count a temporary delivery failure

## Trigger

The mail provider reports a temporary bounce below the suppression threshold.

## Outcome

The temporary-failure count increases while the address remains mailable.
