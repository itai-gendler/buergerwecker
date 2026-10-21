---
kind: primary
routes:
  main: Main
steps:
- text: The platform supplies a changed push destination.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device
  unattended: true
- text: The existing device awaits a setup push for its new destination; existing alerts resume delivery after verification.
  kind: product
  entities:
  - entity: push-device
    effect: changes
    from: Verified
    to: Unverified
    facts:
    - Push destination
    - Verification
    - Last activity
  contexts:
    main:
      place: mobile-app::device
---

# Reverify a changed push destination

## Trigger

The platform supplies a changed push destination.

## Outcome

The existing device awaits a setup push for its new destination; existing alerts resume delivery after verification.
