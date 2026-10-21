---
availability:
- place: website::administration
references:
- kind: code
  role: implementation
  target: app/housekeeping.py#_send_summary_email
- kind: code
  role: implementation
  target: app/admin.py#summary_anomalies
---

# Send operations summary

Email an exception-based operations summary when housekeeping detects anomalies, and a weekly all-clear after a quiet period without a summary.
