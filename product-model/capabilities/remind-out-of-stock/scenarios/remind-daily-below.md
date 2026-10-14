---
kind: alternative
routes:
  app: Android app
steps:
- text: A daily out of stock reminder's time arrives while the stock is at or below its threshold
  kind: condition
  unattended: true
  entities:
  - {entity: medicine, effect: reads, facts: [Stock amount]}
  - {entity: out-of-stock-reminder, effect: reads, facts: [Reminder threshold, Time, Enabled]}
  contexts:
    app:
      place: android-app::stock-notification
- text: The Product records a raised out-of-stock notice and notifies it
  kind: product
  entities:
  - {entity: reminder-event, effect: creates, to: Raised, facts: [Medicine name, Dosage, Type, Reminded time, Notes, Tags, Color and icon, Stock before, Stock after, Remaining repeats, Cannot be skipped, Asks for dosage]}
  contexts:
    app:
      place: android-app::stock-notification
---

# Remind daily while below the threshold

## Trigger

The stock stays low.

## Outcome

The notice repeats once a day until the stock is refilled.
