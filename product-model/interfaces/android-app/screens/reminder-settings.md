---
entities:
- {entity: time-based-reminder, shows: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Time, Weekdays, Days of month, First cycle start, Active days, Pause days], collects: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Weekdays, Days of month, First cycle start, Active days, Pause days]}
- {entity: linked-reminder, shows: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Delay], collects: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority]}
- {entity: interval-reminder, shows: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Interval, Interval start time, Interval start condition], collects: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Interval, Interval start time, Interval start condition]}
- {entity: windowed-interval-reminder, shows: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Interval, Daily start time, Daily end time, Interval start condition], collects: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Interval, Daily start time, Daily end time, Interval start condition]}
- {entity: out-of-stock-reminder, shows: [Reminder threshold, Out of stock reminder], collects: [Reminder threshold, Out of stock reminder]}
- {entity: expiration-reminder, shows: [Expiration reminder, Remind days before expiration], collects: [Expiration reminder, Remind days before expiration]}
- {entity: medicine, shows: [Stock amount, Expiration date]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/advancedReminderPreferences/AdvancedReminderPreferencesRootFragment.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/advancedReminderPreferences/AdvancedReminderPreferencesStock.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/advancedReminderPreferences/ReminderDataStore.kt#ReminderDataStore
- kind: code
  role: implementation
  target: feature/ui/src/main/res/xml/advanced_reminder_settings_root.xml
- kind: code
  role: implementation
  target: feature/ui/src/main/res/xml/advanced_reminder_settings_stock.xml
---

# Advanced settings

One reminder's settings, with its pages for the active date range, dosing instructions and cyclic schedule: whether it is enabled, its timing (weekdays, days of month and cycle for a time based reminder, interval and start for interval reminders, threshold or days before expiry for stock reminders), dosage entry, automatic taking and notification priority, and the control to add a reminder for the following dose.
