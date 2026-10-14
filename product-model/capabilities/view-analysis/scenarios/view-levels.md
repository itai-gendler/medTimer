---
kind: alternative
routes:
  app: Android app
steps:
- text: The User picks Levels
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app::analysis
- text: The Product estimates over the range the relative level of each medicine with a half-life and time to peak from its taken doses
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Taken or skipped time]}
  - {entity: medicine, effect: reads, facts: [Name, Half-life, Time to peak]}
  contexts:
    app:
      place: android-app::analysis
---

# View estimated levels

## Trigger

The User wants an idea of how much of a medicine is in their body.

## Outcome

A level curve per medicine is shown with a disclaimer that it is not medical advice.

## Edge cases

- Doses whose dosage has no readable number are left out and counted.
- A medicine whose doses use different units or more than one number is not shown, with the reason.
