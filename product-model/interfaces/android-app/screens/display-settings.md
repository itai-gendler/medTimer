---
entities:
- {entity: settings, shows: [Big notification buttons, Combine same time notifications, Relative date/time, Show taken time in overview, Show reminded time in overview, Show stock changes in overview, Use system setting for date/time format, Theme], collects: [Big notification buttons, Combine same time notifications, Relative date/time, Show taken time in overview, Show reminded time in overview, Show stock changes in overview, Use system setting for date/time format, Theme]}
references:
- kind: code
  role: implementation
  target: feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/preferences/DisplaySettingsFragment.kt
- kind: code
  role: implementation
  target: feature/ui/src/main/res/xml/display_settings.xml
---

# Display settings

How notifications and the Overview present reminders, the date and time format, and the theme.
