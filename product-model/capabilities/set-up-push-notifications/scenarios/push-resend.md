---
kind: edge
routes:
  main: Main
steps:
- text: The resident chooses Resend while setup is waiting.
  kind: actor
  entities: []
  actor: resident
  contexts:
    main:
      place: mobile-app::public::setup
- text: A fresh setup push is requested and the app waits for acknowledgement.
  kind: product
  entities:
  - entity: push-device
    effect: changes
    facts:
    - Verification
  actor: resident
  contexts:
    main:
      place: mobile-app::public::setup
---

# Request a replacement setup push

## Trigger

The resident chooses Resend while setup is waiting.

## Outcome

A fresh setup push is requested and the app waits for acknowledgement.

## Edge cases

- The previous code is replaced.
- A resend within the waiting interval shows the remaining wait; normal minimum spacing is one minute.
- A wrong or expired code leaves setup waiting and offers Resend.
- A platform registration or integrity-service failure is shown as a setup problem.
