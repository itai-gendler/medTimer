---
kind: primary
routes:
  app: Android app
steps:
- text: The User opens Privacy settings and changes them
  kind: actor
  actor: user
  entities:
  - {entity: settings, effect: reads, facts: [Block screen capture, Require authentication to open the app, Hide medication name in notification, Disable home screen widgets]}
  contexts:
    app:
      place: android-app::privacy-settings
- text: The Product keeps the new values
  kind: product
  actor: user
  entities:
  - {entity: settings, effect: changes, facts: [Block screen capture, Require authentication to open the app, Hide medication name in notification, Disable home screen widgets]}
  contexts:
    app:
      place: android-app::privacy-settings
---

# Privacy settings

## Trigger

The User wants their medication kept from others who see the phone.

## Outcome

The app and its notifications follow the new privacy settings.

## Edge cases

- Require authentication to open the app can only be switched on where the device offers biometrics or a screen lock.
