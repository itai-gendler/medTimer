---
entities:
- {entity: settings, shows: [Repeat reminders, Number of repetitions, Time between repetitions], collects: [Repeat reminders, Number of repetitions, Time between repetitions]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/preferences/RepeatRemindersPreferencesFragment.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/res/xml/repeat_reminders_preferences.xml
---

# Repeat reminders

Whether an unanswered reminder is repeated, how often and how far apart.
