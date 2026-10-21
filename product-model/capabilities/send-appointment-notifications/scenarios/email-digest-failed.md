---
kind: edge
routes:
  main: Main
steps:
- text: The configured mail delivery chain cannot deliver the candidate email.
  kind: condition
  entities: []
  contexts:
    main:
      place: website::subscription
  unattended: true
- text: No successful notification is recorded; later cycles may notify about still-available candidates.
  kind: product
  entities: []
  contexts:
    main:
      place: website::subscription
---

# Retry after an email delivery failure

## Trigger

The configured mail delivery chain cannot deliver the candidate email.

## Outcome

No successful notification is recorded; later cycles may notify about still-available candidates.

## Edge cases

- Mail falls through the configured provider order when a provider cannot deliver.
- Recipient-specific rejection does not prevent other recipients being served.
