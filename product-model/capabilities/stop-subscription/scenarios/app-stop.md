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
      place: mobile-app::device::alerts
- text: The search is ended and no longer receives appointment notifications.
  kind: product
  entities:
  - entity: app-alert
    effect: changes
    from: Active
    to: Ended
    facts:
    - Active
  actor: resident
  contexts:
    main:
      place: mobile-app::device::alerts
---

# Stop an active search

## Trigger

The resident confirms that this search should stop.

## Outcome

The search is ended and no longer receives appointment notifications.

## Edge cases

- An already absent alert is removed from the local list.
- After a successful stop following reported slots, or No, I have got one, the app requests the store’s optional rating sheet.
