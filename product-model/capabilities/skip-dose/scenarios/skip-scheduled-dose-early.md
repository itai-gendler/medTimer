---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Skipped on a dose scheduled later in the Overview
  kind: actor
  actor: user
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Dosage, Time]}
  contexts:
    app:
      place: android-app::overview
- text: The Product records the dose as skipped for its scheduled time
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: creates, to: Skipped, facts: [Medicine name, Dosage, Type, Reminded time, Notes, Tags, Color and icon, Stock before, Stock after, Remaining repeats, Cannot be skipped, Asks for dosage, Taken or skipped time]}
  contexts:
    app:
      place: android-app::overview
---

# Skip a scheduled dose in advance

## Trigger

The User knows they will not take a coming dose.

## Outcome

The dose is skipped and its reminder does not notify.
