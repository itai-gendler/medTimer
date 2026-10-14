---
kind: primary
result: achieved
routes:
  app: Android app
steps:
- text: The User chooses Add medicine and enters the medicine name
  kind: actor
  actor: user
  capability: add-medicine
  entities:
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicines
- text: The Product creates the medicine
  kind: product
  actor: user
  capability: add-medicine
  entities:
  - {entity: medicine, effect: creates, facts: [Name, Icon, Notes, Color, Notification priority, Cannot be skipped, Stock amount, Unit, Refill size, Production date, Expiration date, Half-life, Time to peak, Position]}
  contexts:
    app:
      place: android-app::medicines
- text: The Product opens the new medicine
  kind: product
  actor: user
  capability: add-medicine
  entities:
  - {entity: medicine, effect: reads, facts: [Name]}
  contexts:
    app:
      place: android-app::medicine
- text: The User chooses Add reminder, picks Time based reminder and enters the dosage and time
  kind: actor
  actor: user
  capability: add-reminder
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Dosage, Time]}
  contexts:
    app:
      place: android-app::new-reminder
- text: The Product creates the reminder
  kind: product
  actor: user
  capability: add-reminder
  entities:
  - {entity: time-based-reminder, effect: creates, facts: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Time, Weekdays, Days of month, First cycle start, Active days, Pause days]}
  contexts:
    app:
      place: android-app::new-reminder
---

# Add a medicine and its first reminder

## Trigger

The User starts a new medicine.

## Outcome

The medicine exists with a reminder at its time.
