---
kind: primary
routes:
  main: Main
steps:
- text: The resident submits a reply address and nonempty message.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: website::public::contact
- text: The message is sent to the operator and success is shown.
  kind: product
  entities:
  - entity: operator
    effect: reads
    facts: []
  actor: resident
  contexts:
    main:
      place: website::public::contact
---

# Send a contact message

## Trigger

The resident submits a reply address and nonempty message.

## Outcome

The message is sent to the operator and success is shown.

## Edge cases

- Equivalent double submissions within the same ten-minute bucket are deduplicated.
- Names are bounded to 200 characters and messages to 5000 characters.
