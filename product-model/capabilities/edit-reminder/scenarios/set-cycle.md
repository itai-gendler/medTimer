---
kind: alternative
routes:
  app: Android app
steps:
- text: The User opens Cyclic reminder in Advanced settings and sets the first cycle start, active days and pause days
  kind: actor
  actor: user
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [First cycle start, Active days, Pause days]}
  contexts:
    app:
      place: android-app::reminder-settings
- text: The Product keeps the cycle
  kind: product
  actor: user
  entities:
  - {entity: time-based-reminder, effect: changes, facts: [First cycle start, Active days, Pause days]}
  contexts:
    app:
      place: android-app::reminder-settings
---

# Make a reminder cyclic

## Trigger

The User takes a medicine in cycles, such as 21 days on and 7 days off.

## Outcome

The reminder notifies only on the active days of each cycle counted from the first cycle start.

## Edge cases

- A reminder every n days or weeks is a cycle of 1 active day and n - 1 pause days.
