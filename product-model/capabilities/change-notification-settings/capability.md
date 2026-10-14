---
domain: settings
availability:
- {place: android-app}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/preferences/NotificationSettingsFragment.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/res/xml/notification_settings.xml
---

# Notification and reminder settings

The User sets how reminder notifications behave: always playing the sound, the action when dismissing a notification, whether reminders can be skipped, persistence on the lock screen and exact reminders; the system settings of each notification priority are reached from here.
