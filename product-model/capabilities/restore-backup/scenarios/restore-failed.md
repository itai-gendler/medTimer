---
kind: edge
routes:
  app: Android app
steps:
- text: The User picks a file that is not a valid backup
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app
- text: The Product says the restore failed
  kind: product
  actor: user
  entities: []
  contexts:
    app:
      place: android-app
---

# Restore fails

## Trigger

The file cannot be read as a backup.

## Outcome

Medicines and events stay as they were.
