---
availability:
- place: website::subscription
- place: mobile-app::device
references:
- kind: code
  role: implementation
  target: app/cycle.py#run_cycle
- kind: code
  role: implementation
  target: app/digest.py#flush_digests
- kind: code
  role: implementation
  target: app/digest.py#render_digest_text
- kind: code
  role: implementation
  target: app/push.py#render_push
domain: subscriptions
---

# Send appointment notifications

Notify active searches about new matching opportunities by their channel. Email and push use the same per-subscription rolling limit and adaptive cadence. Deferred candidates are reconsidered from live polls rather than stored for later sending.
