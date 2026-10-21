---
kind: edge
routes:
  main: Main
steps:
- text: The widget refresh finds that registration access has ended.
  kind: condition
  unattended: true
  entities: []
  contexts:
    main:
      place: mobile-app::device::widget
- text: The Product clears the widget display and asks for the app to be opened.
  kind: product
  entities: []
  contexts:
    main:
      place: mobile-app::device::widget
---

# Request opening the app after registration access ends

## Trigger

The widget refresh finds that its registration no longer gives access.

## Outcome

The widget clears the old displayed data and asks the resident to open the app.
