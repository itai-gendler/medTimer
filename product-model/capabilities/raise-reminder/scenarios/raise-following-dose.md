---
kind: alternative
routes:
  app: Android app
steps:
- text: The delay of a linked reminder has passed since the dose it follows was taken or skipped
  kind: condition
  unattended: true
  entities:
  - {entity: linked-reminder, effect: reads, facts: [Delay, Enabled]}
  contexts:
    app:
      place: android-app::reminder-notification
- text: The Product records a raised event for the following dose and notifies it
  kind: product
  entities:
  - {entity: reminder-event, effect: creates, to: Raised, facts: [Medicine name, Dosage, Type, Reminded time, Notes, Tags, Color and icon, Stock before, Stock after, Remaining repeats, Cannot be skipped, Asks for dosage]}
  contexts:
    app:
      place: android-app::reminder-notification
---

# Raise a following dose

## Trigger

The previous dose of a sequence was answered.

## Outcome

The following dose notifies after its delay.
