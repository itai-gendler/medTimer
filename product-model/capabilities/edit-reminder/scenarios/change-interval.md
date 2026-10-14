---
kind: alternative
routes:
  app: Android app
steps:
- text: The User changes the interval, the interval start time or the interval start condition in Advanced settings
  kind: actor
  actor: user
  entities:
  - {entity: interval-reminder, effect: reads, facts: [Interval, Interval start time, Interval start condition]}
  contexts:
    app:
      place: android-app::reminder-settings
- text: The Product keeps the new interval settings
  kind: product
  actor: user
  entities:
  - {entity: interval-reminder, effect: changes, facts: [Interval, Interval start time, Interval start condition]}
  contexts:
    app:
      place: android-app::reminder-settings
---

# Change an interval reminder

## Trigger

The interval changes.

## Outcome

The next reminders follow the new interval; to change the interval cleanly the start time is set to the next reminder time.
