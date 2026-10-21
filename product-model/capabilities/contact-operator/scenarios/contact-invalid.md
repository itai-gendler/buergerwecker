---
kind: validation
routes:
  main: Main
steps:
- text: The resident submits an invalid email address or empty message.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: website::public::contact
- text: The form reports the input problem.
  kind: product
  entities: []
  actor: resident
  contexts:
    main:
      place: website::public::contact
---

# Reject an incomplete contact message

## Trigger

The resident submits an invalid email address or empty message.

## Outcome

The form reports the input problem.
