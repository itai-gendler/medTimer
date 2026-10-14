---
entities:
- {entity: settings, shows: [Weekend mode, Weekend days, Weekend start time, Weekend end time], collects: [Weekend mode, Weekend days, Weekend start time, Weekend end time]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/preferences/WeekendModePreferencesFragment.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/res/xml/weekend_mode_preferences.xml
---

# Weekend mode

Whether reminders falling in a time range on chosen days are delayed to its end, the days and the range.
