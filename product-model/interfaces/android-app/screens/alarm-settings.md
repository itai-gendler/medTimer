---
entities:
- {entity: settings, shows: [No alarm sound when silent, No vibration when silent, Alarm ringtone], collects: [No alarm sound when silent, No vibration when silent, Alarm ringtone]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/preferences/AlarmSettingsFragment.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/res/xml/alarm_settings.xml
---

# Alarm settings

The ringtone of alarm reminders and whether they stay silent or still when the phone is silent.
