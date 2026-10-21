---
availability:
- place: website::administration
references:
- kind: code
  role: implementation
  target: app/housekeeping.py#_prune_suppressions
- kind: code
  role: implementation
  target: app/housekeeping.py#_prune_email_failures
---

# Remove expired delivery block

Remove old delivery standing according to its reason: complaint suppression has a configured retention period, while other records expire after their last associated subscription is purged.
