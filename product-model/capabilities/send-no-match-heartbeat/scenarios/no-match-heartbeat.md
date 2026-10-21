---
kind: primary
routes:
  main: Main
steps:
- text: An active email request is past a 30- or 60-day milestone without a notification in that milestone window.
  kind: condition
  entities: []
  contexts:
    main:
      place: website::subscription
  unattended: true
- text: The subscriber receives a still-subscribed message and actions to adjust or stop the search.
  kind: product
  entities:
  - entity: email-subscription
    effect: reads
    facts:
    - Email address
    - Language
    - Last notified
  contexts:
    main:
      place: website::subscription
---

# Explain continued silence

## Trigger

An active email request is past a 30- or 60-day milestone without a notification in that milestone window.

## Outcome

The subscriber receives a still-subscribed message and actions to adjust or stop the search.

## Edge cases

- A milestone is marked complete only after successful delivery.
- If both milestones are overdue, the later one waits at least a day after the first.
- Milestones count from confirmation, so a subscription reaches one only if it has been renewed past that age.
