---
kind: primary
routes:
  main: Main
steps:
- text: Housekeeping finds a complaint older than its configured retention, or a non-complaint block with no remaining subscription.
  kind: condition
  entities: []
  contexts:
    main:
      place: website::administration::status
  unattended: true
- text: The retained email delivery block is removed.
  kind: product
  entities:
  - entity: email-delivery
    effect: removes
    from: Blocked
  contexts:
    main:
      place: website::administration::status
---

# Remove a suppression after retention

## Trigger

Housekeeping finds a complaint older than its configured retention, or a non-complaint block with no remaining subscription.

## Outcome

The retained email delivery block is removed.

## Edge cases

- Complaint retention defaults to 365 days.
