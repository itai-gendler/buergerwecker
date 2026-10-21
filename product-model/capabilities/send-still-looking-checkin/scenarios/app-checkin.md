---
kind: primary
routes:
  main: Main
steps:
- text: An active term enters the configured reminder window and no check-in has been delivered for that term.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device
  unattended: true
- text: The still-looking question is delivered and the current term records that its check-in was sent.
  kind: product
  entities:
  - entity: app-alert
    effect: changes
    facts:
    - Check-in sent
  contexts:
    main:
      place: mobile-app::device
---

# Ask before the app term ends

## Trigger

An active term enters the configured reminder window and no check-in has been delivered for that term.

## Outcome

The still-looking question is delivered and the current term records that its check-in was sent.

## Edge cases

- A failed or deferred check-in remains eligible on a later daily run within the reminder window.
