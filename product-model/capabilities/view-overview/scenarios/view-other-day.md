---
kind: alternative
routes:
  app: Android app
steps:
- text: The User moves to another day or week in the week strip
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app::overview
- text: The Product lists the events of that day, or for a future day the doses scheduled for it
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  - {entity: time-based-reminder, effect: reads, facts: [Dosage, Time]}
  contexts:
    app:
      place: android-app::overview
---

# View another day

## Trigger

The User checks a past or coming day.

## Outcome

The chosen day's events or scheduled doses are listed.
