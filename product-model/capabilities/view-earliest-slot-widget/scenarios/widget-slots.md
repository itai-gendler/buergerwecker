---
kind: primary
routes:
  main: Main
steps:
- text: The resident views the home-screen widget.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::device::widget
- text: The earliest matching observed opportunity and its as-of time are shown; tapping opens the app.
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
  actor: resident
  contexts:
    main:
      place: mobile-app::device::widget
---

# Read the home-screen appointment view

## Trigger

The resident views the home-screen widget.

## Outcome

The earliest matching observed opportunity and its as-of time are shown; tapping opens the app.

## Edge cases

- No eligible alerts prompts setup.
- No matching slot is distinct from no data yet.
- Only slots in the server’s bounded snapshot can be considered.
