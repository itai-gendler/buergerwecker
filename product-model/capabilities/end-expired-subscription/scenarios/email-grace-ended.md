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
      place: website::subscription
  unattended: true
- text: The saved search is ended and removed from active management results.
  kind: product
  entities:
  - entity: email-subscription
    effect: changes
    from: Expired
    to: Ended
    facts: []
  contexts:
    main:
      place: website::subscription
---

# End the email search after grace

## Trigger

Housekeeping finds a search whose expiry is older than the configured grace period.

## Outcome

The saved search is ended and removed from active management results.
