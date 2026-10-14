---
entities:
- {entity: medicine, shows: [Name]}
- {entity: reminder-event, shows: [Medicine name, Dosage, Reminded time, Taken or skipped time]}
- {entity: time-based-reminder, shows: [Dosage, Time]}
- {entity: linked-reminder, shows: [Dosage]}
- {entity: interval-reminder, shows: [Dosage]}
- {entity: windowed-interval-reminder, shows: [Dosage]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/statistics/CalendarFragment.kt#CalendarFragment
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/statistics/CalendarEventsProvider.kt#CalendarEventsProvider
---

# Calendar

A month calendar of one medicine: its past events and the days its reminders will notify, with the reminders of a selected day.
