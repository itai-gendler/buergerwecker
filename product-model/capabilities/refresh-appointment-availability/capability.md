---
availability:
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/cycle.py#run_cycle
- kind: code
  role: implementation
  target: app/planning.py#build_plans
- kind: code
  role: implementation
  target: app/snapshots.py#record_snapshots
---

# Refresh appointment availability

Poll due cities for services needed by active subscriptions, sharing identical polling work. Publish a service snapshot only after all of its polling plans succeed.
