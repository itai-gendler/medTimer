---
entities:
- {entity: reminder-event, shows: [Medicine name, Dosage, Type, Reminded time, Taken or skipped time, Notes, Tags, Color and icon, Stock before, Stock after, Cannot be skipped]}
- {entity: medicine, shows: [Name, Icon, Color]}
- {entity: time-based-reminder, shows: [Dosage, Time, Instructions]}
- {entity: linked-reminder, shows: [Dosage, Instructions]}
- {entity: interval-reminder, shows: [Dosage, Instructions]}
- {entity: windowed-interval-reminder, shows: [Dosage, Instructions]}
- {entity: out-of-stock-reminder, shows: [Reminder threshold]}
- {entity: expiration-reminder, shows: [Remind days before expiration]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/OverviewScreen.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/OverviewViewModel.kt#OverviewViewModel
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/OverviewFragment.kt#OverviewFragment
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/actions/ReminderEventActions.kt#ReminderEventActions
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/actions/ScheduledReminderActions.kt#ScheduledReminderActions
---

# Overview

One day of reminders: the events already raised, taken, skipped or acknowledged that day and the doses still scheduled for it, with a week strip to move between days, status filters (taken, skipped, scheduled, raised) and a button to log an additional dose. Events of several days can be selected together.
