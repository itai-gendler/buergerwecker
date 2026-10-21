---
kind: primary
routes:
  main: Main
steps:
- text: Housekeeping finds a search whose expiry is older than the configured grace period.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device
  unattended: true
- text: The saved search is ended and removed from active management results.
  kind: product
  entities:
  - entity: app-alert
    effect: changes
    from: Expired
    to: Ended
    facts:
    - Active
  contexts:
    main:
      place: mobile-app::device
---

# End the app search after grace

## Trigger

Housekeeping finds a search whose expiry is older than the configured grace period.

## Outcome

The saved search is ended and removed from active management results.
