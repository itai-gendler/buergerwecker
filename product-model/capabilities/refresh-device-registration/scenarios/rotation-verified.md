---
kind: edge
routes:
  main: Main
steps:
- text: The replacement setup push is received and acknowledged.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device
  unattended: true
- text: The device is verified again and its existing alerts can be loaded.
  kind: product
  entities:
  - entity: push-device
    effect: changes
    from: Unverified
    to: Verified
    facts:
    - Verification
  contexts:
    main:
      place: mobile-app::device
---

# Resume after the replacement setup push

## Trigger

The replacement setup push is received and acknowledged.

## Outcome

The device is verified again and its existing alerts can be loaded.
