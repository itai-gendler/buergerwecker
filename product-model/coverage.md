---
scope: Email subscriptions, mobile alerts and widgets, appointment matching and delivery, retention, feedback and operator status at the pinned upstream revision.
method: Read-only static tracing of English engineering documents, German and English UI, entry points, persistence, delivery code and selected test assertions.
covered:
- description: Subscription routes, form validation, saved-search persistence and action links.
  paths:
  - app/web.py
  - app/signup.py
  - app/repo.py
  - app/tokens.py
  - app/templates/
- description: Mobile API and bundled client workflows including local inbox, language and data deletion.
  paths:
  - app/api.py
  - client/www/
- description: Native earliest-slot selection and widget observation behavior.
  paths:
  - client/ios/App/BuergerweckerWidget/
  - client/android/app/src/main/java/de/buergerwecker/app/EarliestSlotWidget.java
- description: Catalog interpretation, polling orchestration, matching, snapshots and notification delivery.
  paths:
  - app/catalog.py
  - app/planning.py
  - app/models.py
  - app/filters.py
  - app/cycle.py
  - app/snapshots.py
  - app/digest.py
  - app/confirmations.py
  - app/mail.py
  - app/push.py
- description: Retention, provider feedback, catalog comparison scheduling and operator status.
  paths:
  - app/housekeeping.py
  - app/webhooks.py
  - app/poller.py
  - app/admin.py
  - app/config.py
exclusions:
- description: Build, distribution, signing, dependency packaging and CI tooling are engineering infrastructure.
  paths:
  - .github/
  - scripts/
  - client/package.json
  - client/check-www.js
  - client/android/play.mjs
  - client/ios/asc.mjs
  - client/store-screenshots/
  - Dockerfile.web
  - Dockerfile.poller
  - Dockerfile.backup
  - docker-compose.yml
- description: Art assets, styling and localization wording are presentation rather than product layout requirements.
  paths:
  - client/assets/
  - client/www/style.css
  - app/static/
  - app/i18n/
- description: Tests and fixtures are inspection leads rather than separate product behavior.
  paths:
  - tests/
  - client/test/
- description: Database migration mechanics and HTTP transport plumbing are implementation.
  paths:
  - app/db.py
  - app/http_session.py
unmapped:
- description: Vendor-specific scraping protocols and session recovery beyond the common polling contract are left out to keep the model focused on observable notification behavior.
  paths:
  - app/scrapers/
- description: Every per-city service, office and eligibility note is not enumerated; the shipped catalog remains authoritative vocabulary.
  paths:
  - catalog/
- description: Native secure-storage, platform-integrity and push-plugin internals beyond setup and widget outcomes are left to their platform contracts.
  paths:
  - client/ios/App/App/
  - client/android/app/src/main/java/de/buergerwecker/app/
  - app/integrity.py
- description: Detailed traffic-control algorithms and every telemetry aggregation are outside this product workflow map.
  paths:
  - app/ratelimit.py
  - app/analytics.py
- description: Catalog authoring and repair commands beyond scheduled drift observation remain maintainer tooling.
  paths:
  - app/catalog_sync.py
limitations: []
---

# Coverage
