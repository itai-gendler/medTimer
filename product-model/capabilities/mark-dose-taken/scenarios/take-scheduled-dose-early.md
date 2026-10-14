---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Taken on a dose scheduled later in the Overview
  kind: actor
  actor: user
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Dosage, Time]}
  contexts:
    app:
      place: android-app::overview
- text: The Product records the dose as taken now for its scheduled time and reduces the stock
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: creates, to: Taken, facts: [Medicine name, Dosage, Type, Reminded time, Notes, Tags, Color and icon, Stock before, Stock after, Remaining repeats, Cannot be skipped, Asks for dosage, Taken or skipped time]}
  - {entity: medicine, effect: changes, facts: [Stock amount]}
  contexts:
    app:
      place: android-app::overview
---

# Take a scheduled dose in advance

## Trigger

The User takes a dose before its reminder.

## Outcome

The dose is taken and its reminder does not notify at the scheduled time.
