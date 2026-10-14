---
kind: primary
routes:
  app: Android app
steps:
- text: The User opens the Overview
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app::overview
- text: The Product lists today's events with their state, dosage, reminded and taken time and stock change, and today's scheduled doses not yet raised, in time order
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Type, Reminded time, Taken or skipped time, Tags, Stock before, Stock after]}
  - {entity: time-based-reminder, effect: reads, facts: [Dosage, Time]}
  - {entity: medicine, effect: reads, facts: [Name, Icon, Color]}
  contexts:
    app:
      place: android-app::overview
---

# View today's reminders

## Trigger

The User wants to see what is due and what was done today.

## Outcome

Today's raised, taken, skipped and acknowledged events and scheduled doses are listed.

## Edge cases

- The Overview returns to today when the app is reopened on a later day.
- A battery optimization or exact reminders warning is shown until dismissed; Enable switches exact reminders on.
- With a tag filter set, only events and doses of medicines with a selected tag are listed.
