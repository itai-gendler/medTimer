---
appliesTo:
- {type: entity, id: reminder-event, effect: changes, to: Snoozed until home}
permits:
- actors:
  - user
  when:
  - {entity: settings, fact: Location-based snooze, is: 'On'}
  - {entity: settings, fact: Home location, present: true}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/notificationFactory/NotificationIntentBuilder.kt#NotificationIntentBuilder
- kind: doc
  role: intent
  target: README.md
---

# A dose is snoozed until home only with location-based snooze and a home location

The User snoozes a dose until home only while location-based snooze is on and a home location is set; only then do notifications offer Snooze until home, and only in the variant with Google Play Services.
