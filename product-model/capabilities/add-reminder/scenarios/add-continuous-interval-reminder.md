---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Add reminder and picks Continuous interval reminder
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name]}
  - {entity: interval-reminder, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine
- text: The User enters the dosage, the interval, the interval start time and whether the interval starts when reminded or when taken or skipped
  kind: actor
  actor: user
  entities:
  - {entity: interval-reminder, effect: reads, facts: [Dosage, Interval, Interval start time, Interval start condition]}
  contexts:
    app:
      place: android-app::new-reminder
- text: The Product creates the enabled interval reminder
  kind: product
  actor: user
  entities:
  - {entity: interval-reminder, effect: creates, facts: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Interval, Interval start time, Interval start condition]}
  contexts:
    app:
      place: android-app::new-reminder
---

# Add a continuous interval reminder

## Trigger

The User needs a dose every few hours, independent of the time of day.

## Outcome

The reminder notifies first at the interval start time and then every interval.
