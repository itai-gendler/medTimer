---
domain: settings
singleton: true
references:
- kind: code
  role: implementation
  target: core/domain/src/main/java/com/futsch1/medtimer/core/domain/model/UserPreferences.kt#UserPreferences
- kind: code
  role: implementation
  target: core/domain/src/main/java/com/futsch1/medtimer/core/domain/model/PersistentData.kt
- kind: code
  role: implementation
  target: core/datastore/src/main/java/com/futsch1/medtimer/core/datastore/PreferencesDataSource.kt
---

# App settings

The app-wide settings of the Settings menu, kept once on the device.

## Information kept

- **Always play notification sound** — whether reminder sounds play even when the phone is set to vibrate or do not disturb
- **Action when dismissing notification** — Skip dose, Snooze or Taken: what dismissing a reminder notification does
- **Reminders cannot be skipped** — whether reminder notifications offer no way to skip
- **Persistent reminders on lock screen** — whether reminder notifications cannot be dismissed from the lock screen
- **Exact reminders** — whether reminders are raised at the exact minute
- **Repeat reminders** — whether unanswered reminders are repeated
- **Number of repetitions** — 1 to 5 or unlimited
- **Time between repetitions** — 1 to 60 minutes
- **Snooze duration** — 5, 10, 15, 30 or 60 minutes, or Custom to ask at each snooze
- **Location-based snooze** — whether reminders can be snoozed until arriving home
- **Home location** — the location, with its radius, that counts as home
- **No alarm sound when silent** — whether alarms stay silent while the phone is silent
- **No vibration when silent** — whether alarms do not vibrate while the phone is silent
- **Alarm ringtone** — the sound alarm reminders play
- **Big notification buttons** — whether notifications use big buttons
- **Combine same time notifications** — whether reminders due at the same time share one notification
- **Relative date/time** — whether the Overview shows relative dates and times
- **Show taken time in overview** — whether the Overview shows when doses were taken
- **Show reminded time in overview** — whether the Overview shows when doses were reminded
- **Show stock changes in overview** — whether the Overview shows the stock before and after each dose
- **Use system setting for date/time format** — whether dates and times follow the system format rather than the app language
- **Theme** — Default or Alternative
- **Block screen capture** — whether the app cannot be captured in screenshots
- **Require authentication to open the app** — whether opening the app needs biometrics or the screen lock
- **Hide medication name in notification** — whether notifications show only the first letter of medicine names
- **Disable home screen widgets** — whether the widgets hide reminders
- **Weekend mode** — whether reminders in a time range on chosen days are delayed
- **Weekend days** — the days weekend mode applies to; Saturday and Sunday by default
- **Weekend start time** — the start of the delayed range
- **Weekend end time** — the end of the delayed range, to which reminders are delayed
- **Automatic backup** — Never, Daily, Weekly or Monthly
- **Automatic backup folder** — the folder automatic backups are written to
- **Last automatic backup** — the day of the last automatic backup
- **Tag filter** — the tags the lists are filtered by; none means no filter
