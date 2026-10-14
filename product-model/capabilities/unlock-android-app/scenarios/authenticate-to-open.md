---
kind: primary
routes:
  app: Android app
steps:
- text: Require authentication to open the app is on
  kind: condition
  entities:
  - {entity: settings, effect: reads, facts: [Require authentication to open the app]}
  contexts:
    app:
      place: android-app::unlock
- text: The User opens the app and authenticates with a fingerprint, face or the screen lock
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app::unlock
- text: The Product opens the Overview
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name]}
  contexts:
    app:
      place: android-app::overview
---

# Open the app with authentication

## Trigger

The User opens the app.

## Outcome

The app is open.
