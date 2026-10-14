---
kind: alternative
routes:
  app: Android app
steps:
- text: The User restores a backup file that contains events
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app
- text: The Product replaces the whole history with the events of the file
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, as: old-taken, effect: removes, from: Taken}
  - {entity: reminder-event, as: old-skipped, effect: removes, from: Skipped}
  - {entity: reminder-event, as: restored-taken, effect: creates, to: Taken, facts: [Medicine name, Dosage, Type, Reminded time, Notes, Tags, Color and icon, Stock before, Stock after, Remaining repeats, Cannot be skipped, Asks for dosage, Taken or skipped time]}
  - {entity: reminder-event, as: restored-skipped, effect: creates, to: Skipped, facts: [Medicine name, Dosage, Type, Reminded time, Notes, Tags, Color and icon, Stock before, Stock after, Remaining repeats, Cannot be skipped, Asks for dosage, Taken or skipped time]}
  contexts:
    app:
      place: android-app
---

# Restore event data

## Trigger

The User recovers their history.

## Outcome

The history is the one from the backup.
