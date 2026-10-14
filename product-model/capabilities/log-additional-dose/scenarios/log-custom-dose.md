---
kind: alternative
routes:
  app: Android app
steps:
- text: The User chooses Log additional dose, picks Custom and enters a name, a dosage and the time
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::additional-dose
- text: The Product records a taken additional dose and offers the name and dosage as Recent custom next time
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: creates, to: Taken, facts: [Medicine name, Dosage, Type, Reminded time, Taken or skipped time, Notes]}
  contexts:
    app:
      place: android-app::overview
---

# Log a dose of a custom medicine

## Trigger

The User took something not kept in the app.

## Outcome

The dose is recorded without affecting any stock.
