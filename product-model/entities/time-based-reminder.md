---
domain: medicine
relations:
- entity: reminder-event
  verb: raises
  cardinality: one-to-many
- entity: linked-reminder
  verb: is followed by
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
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/StandardScheduling.kt#StandardScheduling
---

# Time based reminder

A reminder at a time of day, every day or limited to weekdays, days of the month or a cycle of active and
pause days.

## Information kept

- **Dosage** — the amount to take as the person writes it, such as "1 pill" or "75 mg"; its first number is what stock tracking deducts
- **Enabled** — whether the reminder notifies at all; a disabled reminder keeps its configuration
- **Active from** — the first date the reminder may notify, if limited
- **Active until** — the last date the reminder may notify, if limited
- **Instructions** — dosing instructions shown with the reminder, such as "before the meal"
- **Enter dosage when taken** — whether the person is asked for the dosage actually taken when they mark the dose taken
- **Automatically mark as taken** — whether the dose is recorded as taken at its time without a notification, for example to only track stock
- **Notification priority** — Same as medicine, Default, High or High + Alarm
- **Time** — the time of day it notifies
- **Weekdays** — the days of the week it notifies on; all days when none are chosen
- **Days of month** — the days of the month it notifies on; all days when none are chosen
- **First cycle start** — the first day of its first cycle, when it is cyclic
- **Active days** — how many days of each cycle it notifies
- **Pause days** — how many days of each cycle it pauses; zero means it is not cyclic
