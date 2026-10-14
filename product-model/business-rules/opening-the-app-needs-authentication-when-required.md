---
appliesTo:
- {type: capability, id: unlock-android-app}
- {type: entity, id: settings, facts: [Require authentication to open the app]}
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/futsch1/medtimer/MainActivity.kt#MainActivity
- kind: code
  role: implementation
  target: app/src/main/java/com/futsch1/medtimer/Biometrics.kt#Biometrics
---

# Opening the app needs authentication while it is required

While Require authentication to open the app is on, the app shows nothing until the User authenticates with the device's biometrics or screen lock, and closes when authentication is cancelled.
