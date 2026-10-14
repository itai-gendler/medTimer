---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Automatic backup and picks Never
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app
- text: The Product stops automatic backups
  kind: product
  actor: user
  entities:
  - {entity: settings, effect: changes, facts: [Automatic backup]}
  contexts:
    app:
      place: android-app
---

# Turn automatic backup off

## Trigger

The User no longer wants automatic backups.

## Outcome

No more automatic backups are written.
