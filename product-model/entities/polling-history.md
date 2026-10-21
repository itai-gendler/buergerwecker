---
references:
- kind: code
  role: implementation
  target: app/cycle.py#run_cycle
- kind: code
  role: implementation
  target: app/housekeeping.py
- kind: code
  role: implementation
  target: app/admin.py
---

# Polling history

The operational observations used to explain service health to the operator.

## Information kept

- **Latest poll** — Latest poll time by city and observed availability.
- **Failures** — Sustained poll failures and empty-result periods.
- **Catalog differences** — Watched service or office identifiers missing from current upstream catalogs.
- **Maintenance** — Housekeeping and backup times and recent operational alerts.
