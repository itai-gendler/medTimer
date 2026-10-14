---
kind: primary
routes:
  app: Android app
steps:
- text: A tab of the app is shown and a day, a week or 30 days have passed since the last automatic backup
  kind: condition
  unattended: true
  entities:
  - {entity: settings, effect: reads, facts: [Automatic backup, Last automatic backup, Automatic backup folder]}
  contexts:
    app:
      place: android-app
- text: The Product writes the medicines, events and settings to a new file in the folder, notes the day and says where it saved it
  kind: product
  entities:
  - {entity: settings, effect: changes, facts: [Last automatic backup]}
  - {entity: medicine, effect: reads, facts: [Name]}
  - {entity: reminder-event, effect: reads, facts: [Medicine name]}
  contexts:
    app:
      place: android-app
---

# Write a due automatic backup

## Trigger

An automatic backup is due.

## Outcome

A backup file is in the folder.
