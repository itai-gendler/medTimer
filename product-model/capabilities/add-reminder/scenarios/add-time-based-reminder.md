---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Add reminder on the medicine and picks Time based reminder
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name]}
  - {entity: time-based-reminder, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine
- text: The User enters the dosage and the time and chooses Create reminder
  kind: actor
  actor: user
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Dosage, Time]}
  contexts:
    app:
      place: android-app::new-reminder
- text: The Product creates the enabled reminder, notifying every day from tomorrow on unless the time is still ahead today
  kind: product
  actor: user
  entities:
  - {entity: time-based-reminder, effect: creates, facts: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Time, Weekdays, Days of month, First cycle start, Active days, Pause days]}
  contexts:
    app:
      place: android-app::new-reminder
---

# Add a time based reminder

## Trigger

The User needs a daily dose at a fixed time.

## Outcome

The reminder is listed on the medicine and notifies at its time each day.

## Edge cases

- While the medicine tracks stock, a dosage without a number is flagged because it cannot reduce the stock.
