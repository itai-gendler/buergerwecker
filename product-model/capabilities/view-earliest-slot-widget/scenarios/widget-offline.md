---
kind: edge
routes:
  main: Main
steps:
- text: A widget refresh has no network or receives a temporary service or read-budget failure.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device::widget
  unattended: true
- text: The last successful answer remains with its as-of time, or no data yet is shown if none exists.
  kind: product
  entities:
  - entity: free-slot
    effect: reads
    facts:
    - City and office group
    - Appointment type
    - Office
    - Date
    - Time
    - Last checked
  contexts:
    main:
      place: mobile-app::device::widget
---

# Retain dated observations during a temporary failure

## Trigger

A widget refresh has no network or receives a temporary service or read-budget failure.

## Outcome

The last successful answer remains with its as-of time, or no data yet is shown if none exists.

## Edge cases

- A cached appointment whose start has passed is no longer presented as available.
- If access to one city has ended, that city drops out until the app supplies a new alert list.
