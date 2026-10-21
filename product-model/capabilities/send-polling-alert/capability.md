---
availability:
- place: website::administration
references:
- kind: code
  role: implementation
  target: app/housekeeping.py#_check_parser_canary
- kind: code
  role: implementation
  target: app/poller.py#_maybe_alert
---

# Send polling alert

Notify the operator of sustained failing city polls, or a vendor-wide empty result across at least two actively watched non-failing cities. The parser check uses a fixed daily checking window.
