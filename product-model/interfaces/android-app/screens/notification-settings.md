---
entities:
- {entity: settings, shows: [Always play notification sound, Action when dismissing notification, Reminders cannot be skipped, Persistent reminders on lock screen, Exact reminders], collects: [Always play notification sound, Action when dismissing notification, Reminders cannot be skipped, Persistent reminders on lock screen, Exact reminders]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/preferences/NotificationSettingsFragment.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/res/xml/notification_settings.xml
---

# Notification and reminder settings

How reminder notifications behave: the system notification settings of the default, high and out-of-stock priorities, always playing the sound, the action when a notification is dismissed, whether reminders can be skipped, persistence on the lock screen, exact timing and battery optimization, and the way to the repeat settings.
