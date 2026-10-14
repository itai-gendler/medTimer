---
kind: alternative
routes:
  app: Android app
steps:
- text: The User switches Location-based snooze on, allows location access and chooses Home location
  kind: actor
  actor: user
  entities:
  - {entity: settings, effect: reads, facts: [Location-based snooze, Home location]}
  contexts:
    app:
      place: android-app::snooze-settings
- text: The Product determines the device's current location and asks to confirm it as home
  kind: product
  actor: user
  entities:
  - {entity: settings, effect: reads, facts: [Home location]}
  contexts:
    app:
      place: android-app::snooze-settings
- text: The User confirms
  kind: actor
  actor: user
  entities: []
  contexts:
    app:
      place: android-app::snooze-settings
- text: The Product keeps the home location
  kind: product
  actor: user
  entities:
  - {entity: settings, effect: changes, facts: [Location-based snooze, Home location]}
  contexts:
    app:
      place: android-app::snooze-settings
---

# Set the home location

## Trigger

The User wants to be reminded on arriving home.

## Outcome

Notifications offer Snooze until home.

## Edge cases

- Without Google Play Services the Product says location-based snooze is not available.
- If the location cannot be determined the Product says so and keeps the previous home location.
