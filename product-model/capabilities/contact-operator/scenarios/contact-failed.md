---
kind: edge
routes:
  main: Main
steps:
- text: The resident submits a message while the mail chain cannot deliver.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: website::public::contact
- text: A retryable contact failure is shown.
  kind: product
  entities: []
  actor: resident
  contexts:
    main:
      place: website::public::contact
---

# Report a contact delivery failure

## Trigger

The resident submits a message while the mail chain cannot deliver.

## Outcome

A retryable contact failure is shown.
