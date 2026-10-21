---
kind: primary
routes:
  main: Main
steps:
- text: The resident confirms that this search should stop.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
- text: The search is ended and no longer receives appointment notifications.
  kind: product
  entities:
  - entity: email-subscription
    effect: changes
    from: Active
    to: Ended
    facts: []
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
---

# Stop an active search

## Trigger

The resident confirms that this search should stop.

## Outcome

The search is ended and no longer receives appointment notifications.

## Edge cases

- Opening the web unsubscribe link alone does not end the search.
