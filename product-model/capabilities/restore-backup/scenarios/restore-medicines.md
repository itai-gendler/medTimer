---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Restore, confirms that data will be replaced and picks a backup file
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app
- text: The Product replaces all medicines, reminders and tags with those of the file and applies its settings
  kind: product
  actor: user
  entities:
  - {entity: medicine, as: old, effect: removes}
  - {entity: time-based-reminder, as: old-reminder, effect: removes, with: old}
  - {entity: medicine, as: restored, effect: creates, facts: [Name, Icon, Notes, Color, Notification priority, Cannot be skipped, Stock amount, Unit, Refill size, Production date, Expiration date, Half-life, Time to peak, Position]}
  - {entity: time-based-reminder, as: restored-reminder, effect: creates, facts: [Dosage, Enabled, Active from, Active until, Instructions, Enter dosage when taken, Automatically mark as taken, Notification priority, Time, Weekdays, Days of month, First cycle start, Active days, Pause days], with: restored}
  - {entity: settings, effect: changes, facts: [Always play notification sound, Action when dismissing notification, Reminders cannot be skipped, Persistent reminders on lock screen, Exact reminders, Repeat reminders, Number of repetitions, Time between repetitions, Snooze duration, Location-based snooze, Home location, No alarm sound when silent, No vibration when silent, Alarm ringtone, Big notification buttons, Combine same time notifications, Relative date/time, Show taken time in overview, Show reminded time in overview, Show stock changes in overview, Use system setting for date/time format, Theme, Block screen capture, Require authentication to open the app, Hide medication name in notification, Disable home screen widgets, Weekend mode, Weekend days, Weekend start time, Weekend end time, Automatic backup, Automatic backup folder]}
  - {entity: tag, effect: reads, facts: []}
  contexts:
    app:
      place: android-app
- text: The Product says the restore was successful
  kind: product
  actor: user
  entities: []
  contexts:
    app:
      place: android-app
---

# Restore medicine data

## Trigger

The User sets up a new phone or recovers their data.

## Outcome

The medicines and settings of the backup are in place.
