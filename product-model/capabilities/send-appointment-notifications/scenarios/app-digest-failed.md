---
kind: edge
routes:
  main: Main
steps:
- text: The push relay cannot deliver the candidate notification.
  kind: condition
  entities: []
  contexts:
    main:
      place: mobile-app::device
  unattended: true
- text: No successful notification is recorded; later cycles may notify about still-available candidates.
  kind: product
  entities: []
  contexts:
    main:
      place: mobile-app::device
---

# Retry after a push delivery failure

## Trigger

The push relay cannot deliver the candidate notification.

## Outcome

No successful notification is recorded; later cycles may notify about still-available candidates.

## Edge cases

- A push-platform outage ends attempts for that platform during the cycle.
- Notifications beyond the cycle's push budget wait for the next cycle, longest-waiting first.
