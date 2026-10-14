---
domain: overview
availability:
- {place: android-app}
references:
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/SnoozeProcessor.kt#SnoozeProcessor
- kind: code
  role: implementation
  target: feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/LocationSnoozeProcessor.kt
- kind: code
  role: implementation
  target: core/location/src/full/java/com/futsch1/medtimer/core/location/GmsGeofenceRegistrar.kt
---

# Snooze until home

The User puts a reminder off until they arrive at their home location, where it notifies again. Exists only in the full variant, with Google Play Services, while location-based snooze is on and a home location is set.
