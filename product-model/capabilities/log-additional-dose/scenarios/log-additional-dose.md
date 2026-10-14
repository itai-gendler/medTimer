---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Log additional dose and selects a medicine
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name]}
  contexts:
    app:
      place: android-app::additional-dose
- text: The User selects one of the medicine's dosages or enters one, then the time, or uses the current time
  kind: actor
  actor: user
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Dosage]}
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app::additional-dose
- text: The Product records a taken additional dose and reduces the stock when the medicine tracks it
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: creates, to: Taken, facts: [Medicine name, Dosage, Type, Reminded time, Taken or skipped time, Notes, Tags, Color and icon, Stock before, Stock after]}
  - {entity: medicine, effect: changes, facts: [Stock amount]}
  contexts:
    app:
      place: android-app::overview
---

# Log an additional dose of a medicine

## Trigger

The User took an extra dose.

## Outcome

The dose appears as taken in the Overview on the chosen day and time.

## Edge cases

- With more than four medicines a search field narrows the list.
- Inactive reminders offer their dosages as presets.
