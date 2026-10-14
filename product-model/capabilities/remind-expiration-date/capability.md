---
domain: overview
availability:
- {place: android-app}
references:
- kind: code
  role: implementation
  target: feature/reminders/api/src/main/java/com/futsch1/medtimer/feature/reminders/api/scheduling/ExpirationDateScheduling.kt#ExpirationDateScheduling
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/notificationFactory/ExpirationDateNotificationFactory.kt#ExpirationDateNotificationFactory
---

# Remind expiration

The Product notifies that a medicine expires, once or daily from the set number of days before its expiration date.
