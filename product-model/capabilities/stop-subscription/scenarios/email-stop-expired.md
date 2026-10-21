---
kind: edge
routes:
  main: Main
steps:
- text: The resident stops an expired search.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
- text: The search is ended rather than available for renewal.
  kind: product
  entities:
  - entity: email-subscription
    effect: changes
    from: Expired
    to: Ended
    facts: []
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
---

# Stop an expired search

## Trigger

The resident stops an expired search.

## Outcome

The search is ended rather than available for renewal.
