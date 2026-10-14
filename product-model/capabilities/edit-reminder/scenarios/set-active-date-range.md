---
kind: alternative
routes:
  app: Android app
steps:
- text: The User opens Active date range and switches on Active from or Active until and picks the dates
  kind: actor
  actor: user
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Active from, Active until]}
  contexts:
    app:
      place: android-app::reminder-settings
- text: The Product keeps the date range
  kind: product
  actor: user
  entities:
  - {entity: time-based-reminder, effect: changes, facts: [Active from, Active until]}
  contexts:
    app:
      place: android-app::reminder-settings
---

# Set the active date range

## Trigger

A reminder applies only for a period, for example while tapering off.

## Outcome

The reminder notifies only within the range; adjacent ranges on several reminders hand over from one dosage to the next.
