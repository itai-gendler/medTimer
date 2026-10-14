---
kind: primary
routes:
  app: Android app
steps:
- text: The User opens Calendar from the medicine
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name]}
  contexts:
    app:
      place: android-app::medicine
- text: The Product shows the month with past events and the future days a reminder will notify marked
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time, Taken or skipped time]}
  - {entity: time-based-reminder, effect: reads, facts: [Time, Dosage]}
  contexts:
    app:
      place: android-app::medicine-calendar
- text: The User selects a day
  kind: actor
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  contexts:
    app:
      place: android-app::medicine-calendar
- text: The Product lists the events or scheduled reminders of that day
  kind: product
  actor: user
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time, Taken or skipped time]}
  contexts:
    app:
      place: android-app::medicine-calendar
---

# View a medicine's calendar

## Trigger

The User wants to make sure a cyclic or limited schedule notifies on the right days.

## Outcome

The User sees past and future doses of the medicine by day, one month at a time.

## Edge cases

- The calendar covers one month back and nine months ahead.
