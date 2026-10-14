---
kind: edge
routes:
  app: Android app
steps:
- text: An automatic backup is due but the folder is missing or cannot be written
  kind: condition
  unattended: true
  entities:
  - {entity: settings, effect: reads, facts: [Automatic backup folder]}
  contexts:
    app:
      place: android-app
- text: The Product says automatic backups require a folder and offers to select one
  kind: product
  entities:
  - {entity: settings, effect: reads, facts: [Automatic backup]}
  contexts:
    app:
      place: android-app
---

# Folder no longer available

## Trigger

The folder was removed or its access revoked.

## Outcome

No backup is written until a folder is selected.
