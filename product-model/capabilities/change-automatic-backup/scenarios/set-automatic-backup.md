---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Automatic backup and picks Daily, Weekly or Monthly
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app
- text: The Product asks for a folder for the backups
  kind: product
  actor: user
  entities: []
  contexts:
    app:
      place: android-app
- text: The User selects a folder
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app
- text: The Product keeps the interval and the folder
  kind: product
  actor: user
  entities:
  - {entity: settings, effect: changes, facts: [Automatic backup, Automatic backup folder]}
  contexts:
    app:
      place: android-app
---

# Set up automatic backup

## Trigger

The User wants regular backups without thinking about them.

## Outcome

Backups are written to the folder at the chosen interval.
