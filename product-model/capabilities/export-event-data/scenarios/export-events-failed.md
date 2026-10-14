---
kind: edge
routes:
  app: Android app
steps:
- text: The User chooses an event export
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app
- text: The file cannot be written
  kind: condition
  entities: []
  contexts:
    app:
      place: android-app
- text: The Product says the export failed
  kind: product
  actor: user
  entities: []
  contexts:
    app:
      place: android-app
---

# Export fails

## Trigger

Writing the export fails.

## Outcome

Nothing is shared.
