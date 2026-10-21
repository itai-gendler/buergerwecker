---
kind: edge
routes:
  main: Main
steps:
- text: The resident chooses Keep looking for a previously confirmed request during the grace period.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
- text: The paused search is active for a new term from now.
  kind: product
  entities:
  - entity: email-subscription
    effect: changes
    from: Expired
    to: Active
    facts:
    - End date
    - Check-in sent
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
---

# Resume an expired email search

## Trigger

The resident chooses Keep looking for a previously confirmed request during the grace period.

## Outcome

The paused search is active for a new term from now.
