---
kind: alternative
routes:
  app: Android app
steps:
- text: A reminder whose priority is High + Alarm, directly or through its medicine, is due
  kind: condition
  unattended: true
  entities:
  - {entity: time-based-reminder, effect: reads, facts: [Notification priority]}
  - {entity: medicine, effect: reads, facts: [Notification priority]}
  contexts:
    app:
      place: android-app::reminder-alarm
- text: The Product records a raised event
  kind: product
  entities:
  - {entity: reminder-event, effect: creates, to: Raised, facts: [Medicine name, Dosage, Type, Reminded time, Notes, Tags, Color and icon, Stock before, Stock after, Remaining repeats, Cannot be skipped, Asks for dosage]}
  contexts:
    app:
      place: android-app::reminder-alarm
- text: The Product shows the full-screen alarm with the alarm ringtone
  kind: product
  entities:
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Reminded time]}
  - {entity: settings, effect: reads, facts: [Alarm ringtone, No alarm sound when silent, No vibration when silent]}
  contexts:
    app:
      place: android-app::reminder-alarm
---

# Raise a reminder as an alarm

## Trigger

A dose that must not be missed is due while the phone sleeps.

## Outcome

The alarm rings until it is answered.
