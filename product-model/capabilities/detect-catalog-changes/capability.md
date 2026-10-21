---
availability:
- place: website::administration
references:
- kind: code
  role: implementation
  target: app/housekeeping.py#_sync_catalogs
- kind: code
  role: implementation
  target: app/catalog_sync.py
---

# Detect catalog changes

When catalog comparison is enabled, compare upstream service and office identifiers with the packaged catalog and record missing identifiers used by live subscriptions for the operator.
