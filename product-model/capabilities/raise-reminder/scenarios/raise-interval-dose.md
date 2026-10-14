---
kind: alternative
routes:
  app: Android app
steps:
- text: The interval of a continuous interval reminder has passed since its last dose was reminded, or was taken or skipped, as its start condition says
  kind: condition
  unattended: true
  entities:
  - {entity: interval-reminder, effect: reads, facts: [Interval, Interval start time, Interval start condition, Enabled]}
  contexts:
    app:
      place: android-app::reminder-notification
- text: The Product records a raised event and notifies it
  kind: product
  entities:
  - {entity: reminder-event, effect: creates, to: Raised, facts: [Medicine name, Dosage, Type, Reminded time, Notes, Tags, Color and icon, Stock before, Stock after, Remaining repeats, Cannot be skipped, Asks for dosage]}
  contexts:
    app:
      place: android-app::reminder-notification
---

# Raise an interval dose

## Trigger

An interval comes round.

## Outcome

The next interval dose notifies.

## Edge cases

- After a long gap the reminder resumes with the first interval falling today rather than catching up every missed one.
