---
kind: alternative
routes:
  app: Android app
steps:
- text: A reminder set to Automatically mark as taken is due
  kind: condition
  unattended: true
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Automatically mark as taken]}
  contexts:
    app:
      place: android-app::overview
- text: The Product records the event and marks it taken at once, reducing the stock, without a notification
  kind: product
  entities:
  - {entity: reminder-event, effect: creates, to: Raised, facts: [Medicine name, Dosage, Type, Reminded time, Notes, Tags, Color and icon, Stock before, Stock after, Remaining repeats, Cannot be skipped, Asks for dosage]}
  contexts:
    app:
      place: android-app::overview
- text: The Product marks the event taken and reduces the stock
  kind: product
  entities:
  - {entity: reminder-event, effect: changes, from: Raised, to: Taken, facts: [Taken or skipped time, Stock after]}
  - {entity: medicine, effect: changes, facts: [Stock amount]}
  contexts:
    app:
      place: android-app::overview
---

# Take a dose automatically

## Trigger

The User only tracks another person's stock.

## Outcome

The dose is taken in the history and the stock falls, with no notification.
