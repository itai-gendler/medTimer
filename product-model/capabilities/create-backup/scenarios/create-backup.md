---
kind: primary
routes:
  app: Android app
steps:
- text: The User chooses Backup and keeps medicine data, event data or both selected
  kind: actor
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: []}
  contexts:
    app:
      place: android-app
- text: The Product writes the selected data and the settings to a JSON file and opens the share sheet
  kind: product
  actor: user
  entities:
  - {entity: medicine, effect: reads, facts: [Name, Icon, Notes, Color, Notification priority, Cannot be skipped, Stock amount, Unit, Refill size, Production date, Expiration date, Half-life, Time to peak, Position]}
  - {entity: reminder-event, effect: reads, facts: [Medicine name, Dosage, Type, Reminded time, Notes, Tags, Color and icon, Stock before, Stock after, Remaining repeats, Cannot be skipped, Asks for dosage, Taken or skipped time]}
  - {entity: settings, effect: reads, facts: [Always play notification sound, Action when dismissing notification, Reminders cannot be skipped, Persistent reminders on lock screen, Exact reminders, Repeat reminders, Number of repetitions, Time between repetitions, Snooze duration, Location-based snooze, Home location, No alarm sound when silent, No vibration when silent, Alarm ringtone, Big notification buttons, Combine same time notifications, Relative date/time, Show taken time in overview, Show reminded time in overview, Show stock changes in overview, Use system setting for date/time format, Theme, Block screen capture, Require authentication to open the app, Hide medication name in notification, Disable home screen widgets, Weekend mode, Weekend days, Weekend start time, Weekend end time, Automatic backup, Automatic backup folder]}
  - {entity: tag, effect: reads, facts: [Name]}
  contexts:
    app:
      place: android-app
---

# Create a backup

## Trigger

The User wants a copy of their data, for example to move to another phone.

## Outcome

The backup file is shared where the User chooses.

## Edge cases

- If the file cannot be written the Product says the backup failed.
