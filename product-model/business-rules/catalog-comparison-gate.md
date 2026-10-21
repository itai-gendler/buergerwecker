---
appliesTo:
- type: entity
  id: polling-history
  effect: changes
  facts:
  - Catalog differences
permits:
- unattended: true
  when:
  - entity: service-settings
    fact: Catalog comparison enabled
    is: true
references:
- kind: code
  role: implementation
  target: app/housekeeping.py#_start_catalog_sync
---

# Configured catalog comparison records upstream differences

Daily catalog comparison is available only while its deployment setting is enabled.
