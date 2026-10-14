---
kind: primary
routes:
  app: Android app
steps:
- text: The day is the set number of days before the expiration date or later, at the reminder time
  kind: condition
  unattended: true
  entities:
  - {entity: medicine, effect: reads, facts: [Expiration date]}
  - {entity: expiration-reminder, effect: reads, facts: [Expiration reminder, Remind days before expiration, Time, Enabled]}
  contexts:
    app:
      place: android-app::stock-notification
- text: The Product records a raised expiration notice with the expiration date and notifies that the medicine expires
  kind: product
  entities:
  - {entity: reminder-event, effect: creates, to: Raised, facts: [Medicine name, Dosage, Type, Reminded time, Notes, Tags, Color and icon, Stock before, Stock after, Remaining repeats, Cannot be skipped, Asks for dosage]}
  - {entity: medicine, effect: reads, facts: [Name, Expiration date]}
  contexts:
    app:
      place: android-app::stock-notification
---

# Remind of an expiration date

## Trigger

A medicine approaches its expiration date.

## Outcome

The notification suggests replacing the medicine; Once notifies a single time, Daily every day from then on.
