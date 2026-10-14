---
domain: medicine
relations:
- entity: reminder-event
  verb: raises
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: core/domain/src/main/java/com/futsch1/medtimer/core/domain/model/Reminder.kt#Reminder
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/advancedReminderPreferences/ReminderDataStore.kt#ReminderDataStore
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/IntervalScheduling.kt#IntervalScheduling
---

# Continuous interval reminder

A reminder that repeats at a fixed interval, such as every 10 hours, from a start time, regardless of
the time of day.

## Information kept

- **Dosage** — the amount to take as the person writes it, such as "1 pill" or "75 mg"; its first number is what stock tracking deducts
- **Enabled** — whether the reminder notifies at all; a disabled reminder keeps its configuration
- **Active from** — the first date the reminder may notify, if limited
- **Active until** — the last date the reminder may notify, if limited
- **Instructions** — dosing instructions shown with the reminder, such as "before the meal"
- **Enter dosage when taken** — whether the person is asked for the dosage actually taken when they mark the dose taken
- **Automatically mark as taken** — whether the dose is recorded as taken at its time without a notification, for example to only track stock
- **Notification priority** — Same as medicine, Default, High or High + Alarm
- **Interval** — the time between two reminders, up to a year
- **Interval start time** — the date and time of the first reminder, from which later ones are counted
- **Interval start condition** — whether the next interval starts when the previous reminder was raised or when it was taken or skipped
