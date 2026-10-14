---
kind: edge
routes:
  app: Android app
steps:
- text: The User chooses Create calendar entry
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Estimated run out date]}
  contexts:
    app:
      place: android-app::medicine-stock-settings
- text: No calendar app is installed
  kind: condition
  entities: []
  contexts:
    app:
      place: android-app::medicine-stock-settings
- text: The Product says no calendar app was found
  kind: product
  actor: user
  entities: []
  contexts:
    app:
      place: android-app::medicine-stock-settings
---

# No calendar app

## Trigger

The device has no calendar app.

## Outcome

No entry is created.
