---
kind: primary
routes:
  main: Main
steps:
- text: The resident follows the confirmation link.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
- text: The Product activates the email subscription.
  kind: product
  entities:
  - entity: email-subscription
    effect: changes
    from: Pending
    to: Active
    facts: []
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
- text: The Product shows the term end and attempts the management email.
  kind: product
  entities:
  - entity: email-subscription
    effect: reads
    facts:
    - Email address
    - Language
    - End date
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
---

# Activate a pending subscription

## Trigger

The resident follows the confirmation link before the saved term ends.

## Outcome

The subscription is active. Its end date is shown; the convenience email carries the management link.

## Edge cases

- A full city waitlist leaves a pending request unconfirmed and its link available for a later attempt.
