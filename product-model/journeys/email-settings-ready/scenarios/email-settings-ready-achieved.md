---
kind: primary
result: achieved
routes:
  main: Main
steps:
- text: The resident confirms the saved email subscription.
  kind: actor
  entities:
  - entity: email-subscription
    effect: changes
    from: Pending
    to: Active
    facts: []
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
  capability: confirm-email-subscription
- text: The Product sends the management link and term end.
  kind: product
  entities:
  - entity: email-subscription
    effect: reads
    facts:
    - Email address
    - End date
    - Language
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
  capability: confirm-email-subscription
- text: The resident follows the management link and reads the email subscription.
  kind: actor
  entities:
  - entity: email-subscription
    effect: reads
    facts:
    - City and office group
    - Appointment type
    - Offices
    - Weekdays
    - Time window
    - Days ahead
    - End date
  actor: resident
  contexts:
    main:
      place: website::subscription::subscription
  capability: browse-subscriptions
---

# Confirm, then open the management link

## Trigger

The resident follows the emailed confirmation for a saved request.

## Outcome

The email subscription is active and its management-link destination shows the saved preferences.
