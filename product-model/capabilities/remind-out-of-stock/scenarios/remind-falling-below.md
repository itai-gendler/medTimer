---
kind: primary
routes:
  app: Android app
steps:
- text: A taken dose brings the medicine's stock to or below the threshold of a Once or Always out of stock reminder
  kind: condition
  unattended: true
  entities:
  - {entity: medicine, effect: reads, facts: [Stock amount]}
  - {entity: out-of-stock-reminder, effect: reads, facts: [Reminder threshold, Out of stock reminder, Enabled]}
  contexts:
    app:
      place: android-app::stock-notification
- text: The Product records a raised out-of-stock notice with the stock left and notifies it with a Refill button
  kind: product
  entities:
  - {entity: reminder-event, effect: creates, to: Raised, facts: [Medicine name, Dosage, Type, Reminded time, Notes, Tags, Color and icon, Stock before, Stock after, Remaining repeats, Cannot be skipped, Asks for dosage]}
  - {entity: medicine, effect: reads, facts: [Name, Stock amount, Refill size]}
  contexts:
    app:
      place: android-app::stock-notification
---

# Remind when stock falls to the threshold

## Trigger

A dose is taken while the stock is low.

## Outcome

The out-of-stock notification asks the User to refill soon.

## Edge cases

- Once notifies only the dose that crosses the threshold; Always notifies after every taken dose while at or below it.
