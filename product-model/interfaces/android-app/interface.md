---
type: mobile-app
actors:
- user
references:
- kind: code
  role: implementation
  target: app/src/main/AndroidManifest.xml
- kind: code
  role: implementation
  target: app/src/main/java/com/futsch1/medtimer/MainActivity.kt#MainActivity
- kind: code
  role: implementation
  target: app/src/main/java/com/futsch1/medtimer/AppNavigation.kt#AppNavigationScaffold
- kind: code
  role: implementation
  target: feature/ui/src/main/res/navigation/navigation.xml
---

# Android app

The MedTimer app for Android phones and tablets, together with the reminder notifications and alarms it
posts. It opens on the Overview and has three tabs, Overview, Medicine and Analysis, with the settings,
data export and backup reached from the options menu of each tab.
