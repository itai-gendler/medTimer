---
kind: alternative
routes:
  app: Android app
steps:
- text: The User changes the threshold and type of an out of stock reminder, or the days before expiration and type of an expiration reminder
  kind: actor
  actor: user
  entities:
  - {entity: out-of-stock-reminder, effect: reads, facts: [Reminder threshold, Out of stock reminder]}
  - {entity: expiration-reminder, effect: reads, facts: [Expiration reminder, Remind days before expiration]}
  contexts:
    app:
      place: android-app::reminder-settings
- text: The Product keeps the new values
  kind: product
  actor: user
  entities:
  - {entity: out-of-stock-reminder, effect: changes, facts: [Reminder threshold, Out of stock reminder]}
  - {entity: expiration-reminder, effect: changes, facts: [Expiration reminder, Remind days before expiration]}
  contexts:
    app:
      place: android-app::reminder-settings
---

# Change a stock reminder

## Trigger

The User wants to be warned earlier or more often.

## Outcome

The stock reminders use the new values.
