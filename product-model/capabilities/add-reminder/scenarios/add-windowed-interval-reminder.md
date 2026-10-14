---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Add reminder and picks Windowed interval reminder
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name]}
  - {entity: windowed-interval-reminder, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::medicine
- text: The User enters the dosage, the interval, the daily start and end time and the interval start condition
  kind: actor
  actor: user
  entities:
  - {entity: windowed-interval-reminder, effect: reads, facts: [Dosage, Interval, Daily start time, Daily end time, Interval start condition]}
  contexts:
    app:
      place: android-app::new-reminder
- text: The Product creates the enabled windowed interval reminder
  kind: product
  actor: user
  entities:
  - {entity: windowed-interval-reminder, effect: creates, facts: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Interval, Daily start time, Daily end time, Interval start condition]}
  contexts:
    app:
      place: android-app::new-reminder
---

# Add a windowed interval reminder

## Trigger

The User needs doses at intervals during the day only.

## Outcome

Each day the reminder notifies at the start time and then every interval until the end time.
