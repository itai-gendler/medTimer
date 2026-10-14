---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Duplicate including reminders
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name]}
  contexts:
    app:
      place: android-app::medicine
- text: The Product creates a copy of the medicine, its tags and copies of all its reminders
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: creates, facts: [Name, Icon, Notes, Color, Notification priority, Cannot be skipped, Stock amount, Unit, Refill size, Production date, Expiration date, Half-life, Time to peak, Position]}
  - {entity: time-based-reminder, effect: creates, facts: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Time, Weekdays, Days of month, First cycle start, Active days, Pause days], with: medicine}
  - {entity: linked-reminder, effect: creates, facts: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Delay], with: medicine}
  - {entity: interval-reminder, effect: creates, facts: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Interval, Interval start time, Interval start condition], with: medicine}
  - {entity: windowed-interval-reminder, effect: creates, facts: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Interval, Daily start time, Daily end time, Interval start condition], with: medicine}
  - {entity: out-of-stock-reminder, effect: creates, facts: [Enabled, Reminder threshold, Out of stock reminder, Time], with: medicine}
  - {entity: expiration-reminder, effect: creates, facts: [Enabled, Expiration reminder, Remind days before expiration, Time], with: medicine}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicines
---

# Duplicate a medicine including reminders

## Trigger

The User wants the copy to remind them the same way.

## Outcome

The copy has the same reminders as the original.
