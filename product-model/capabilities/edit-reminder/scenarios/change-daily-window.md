---
kind: alternative
routes:
  app: Android app
steps:
- text: The User changes the interval, daily start time or daily end time of a windowed interval reminder
  kind: actor
  actor: user
  entities:
  - {entity: windowed-interval-reminder, effect: reads, facts: [Interval, Daily start time, Daily end time]}
  contexts:
    app:
      place: android-app::reminder-settings
- text: The Product keeps the new window
  kind: product
  actor: user
  entities:
  - {entity: windowed-interval-reminder, effect: changes, facts: [Interval, Daily start time, Daily end time]}
  contexts:
    app:
      place: android-app::reminder-settings
---

# Change the daily window

## Trigger

The waking hours change.

## Outcome

Reminders follow the new window.
