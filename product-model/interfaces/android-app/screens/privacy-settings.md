---
entities:
- {entity: settings, shows: [Block screen capture, Require authentication to open the app, Hide medication name in notification, Disable home screen widgets], collects: [Block screen capture, Require authentication to open the app, Hide medication name in notification, Disable home screen widgets]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/preferences/PrivacyPreferencesFragment.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/res/xml/privacy_preferences.xml
---

# Privacy settings

Screen capture blocking, authentication to open the app, hiding medicine names in notifications and disabling the home screen widgets.
