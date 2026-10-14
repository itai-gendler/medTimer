---
kind: alternative
routes:
  app: Android app
steps:
- text: The User picks Calendar and selects a day
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app::analysis
- text: The Product shows the events of each day of the month and the details of the selected day
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time, Taken or skipped time]}
  contexts:
    app:
      place: android-app::analysis
---

# View the history calendar

## Trigger

The User checks a particular day.

## Outcome

The day's events are shown.
