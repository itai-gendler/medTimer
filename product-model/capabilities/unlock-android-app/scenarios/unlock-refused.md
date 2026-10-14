---
kind: validation
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
- text: The User cancels the authentication or it fails with an error
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app::unlock
- text: The Product closes the app without showing anything
  kind: product
  actor: user
  entities: []
  contexts:
    app:
      place: android-app::unlock
---

# Authentication cancelled

## Trigger

Someone cannot authenticate.

## Outcome

The app stays closed.
