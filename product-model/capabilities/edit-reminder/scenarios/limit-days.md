---
kind: alternative
routes:
  app: Android app
steps:
- text: The User picks the weekdays or the days of the month the reminder notifies on
  kind: actor
  actor: user
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Weekdays, Days of month]}
  contexts:
    app:
      place: android-app::reminder-settings
- text: The Product keeps the days; choosing none means every day
  kind: product
  actor: user
  entities:
  - {entity: time-based-reminder, effect: changes, facts: [Weekdays, Days of month]}
  contexts:
    app:
      place: android-app::reminder-settings
---

# Limit a reminder to weekdays or days of month

## Trigger

A dose is needed only on some days.

## Outcome

The reminder notifies only on the chosen days.
