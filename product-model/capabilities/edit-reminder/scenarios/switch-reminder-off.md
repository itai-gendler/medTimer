---
kind: alternative
routes:
  app: Android app
steps:
- text: The User switches Reminder enabled off or on
  kind: actor
  actor: user
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Enabled]}
  contexts:
    app:
      place: android-app::reminder-settings
- text: The Product keeps the reminder with the new state
  kind: product
  actor: user
  entities:
  - {entity: time-based-reminder, effect: changes, facts: [Enabled]}
  contexts:
    app:
      place: android-app::reminder-settings
---

# Switch a reminder off or on

## Trigger

The User pauses or resumes one reminder.

## Outcome

A disabled reminder keeps its configuration and does not notify.
