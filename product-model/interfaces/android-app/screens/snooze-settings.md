---
entities:
- {entity: settings, shows: [Snooze duration, Location-based snooze, Home location], collects: [Snooze duration, Location-based snooze, Home location]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/preferences/SnoozeSettingsFragment.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/res/xml/snooze_settings.xml
---

# Snooze settings

How long Snooze delays a reminder, or Custom to ask each time, and location-based snooze with the home location it uses.
