---
kind: edge
routes:
  main: Main
steps:
- text: The resident follows the confirmation link of a pending request within its term.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
- text: The city still has room for the request's service, so the Product activates the email subscription.
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
- text: The Product tries to send the email with the management link and end date, and the mail delivery fails.
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
- text: The success page still shows the end date; the subscription stays active.
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

# Keep confirmation after a mail failure

## Trigger

The resident confirms while the management email cannot be sent.

## Outcome

The saved request is active and the success page shows its end date; the failed management email does not undo or hide the confirmation.
