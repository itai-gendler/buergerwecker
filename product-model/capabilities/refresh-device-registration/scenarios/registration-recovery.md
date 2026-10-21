---
kind: edge
routes:
  main: Main
steps:
- text: The server reports that the stored registration is absent or retired.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device
  unattended: true
- text: The app registers again and waits for setup; alerts ended by retirement remain ended.
  kind: product
  entities:
  - entity: push-device
    effect: creates
    to: Unverified
    facts:
    - Platform
    - Language
    - Push destination
    - Verification
    - Last activity
  contexts:
    main:
      place: mobile-app::device
---

# Recover registration on a later launch

## Trigger

The server reports that the stored registration is absent or retired.

## Outcome

The app registers again and waits for setup; alerts ended by retirement remain ended.

## Edge cases

- Re-registering the same live destination retains its saved alerts once setup succeeds.
- A temporarily unreadable credential is retried later without replacing a working registration.
