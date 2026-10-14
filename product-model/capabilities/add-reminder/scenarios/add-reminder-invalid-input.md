---
kind: validation
routes:
  app: Android app
steps:
- text: The User enters a threshold or number of days that is not a number and chooses Create reminder
  kind: actor
  actor: user
  entities:
  - {entity: out-of-stock-reminder, effect: reads, facts: [Reminder threshold]}
  contexts:
    app:
      place: android-app::new-reminder
- text: The Product says the input is invalid and creates nothing
  kind: product
  actor: user
  entities: []
  contexts:
    app:
      place: android-app::new-reminder
---

# Invalid reminder input

## Trigger

The User leaves a required number unreadable.

## Outcome

No reminder is created; the form stays open.
