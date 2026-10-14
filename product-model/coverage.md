---
scope: 'The MedTimer Android app at ffeb1056ac207e6cb42186572119cc9f749fd46c: medicines, reminders and their scheduling, notifications, the reminder history, stock, tags, analysis, export, backup and settings.'
method: Static inspection of source, resources and documentation; nothing was built or run.
covered:
- description: 'App shell: navigation, app lock, backup and restore, custom snooze, option actions.'
  paths:
  - app/src/main/java/com/futsch1/medtimer/MainActivity.kt
  - app/src/main/java/com/futsch1/medtimer/AppNavigation.kt
  - app/src/main/java/com/futsch1/medtimer/Biometrics.kt
  - app/src/main/java/com/futsch1/medtimer/CustomSnoozeHandler.kt
  - app/src/main/java/com/futsch1/medtimer/AppOptionsActionsImpl.kt
  - app/src/main/java/com/futsch1/medtimer/database/backup/
- description: Domain models and repository contracts.
  paths:
  - core/domain/
- description: Room entities, DAOs and repositories.
  paths:
  - core/database/src/main/
- description: Stored settings and remembered selections.
  paths:
  - core/datastore/
- description: Shared helpers for amounts, reminders and time.
  paths:
  - core/common/src/main/
- description: Location and geofencing for snooze until home, both build variants.
  paths:
  - core/location/
- description: Scheduling, raising and processing of reminders, notifications and alarms.
  paths:
  - feature/reminders/api/
  - feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/command/
  - feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/notificationData/
  - feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/notificationFactory/
  - feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/alarm/
  - feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/NotificationProcessor.kt
  - feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/ReminderNotificationProcessor.kt
  - feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/ScheduleNextReminderNotificationProcessor.kt
  - feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/SnoozeProcessor.kt
  - feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/RepeatProcessor.kt
  - feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/StockHandlingProcessor.kt
  - feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/RefillProcessor.kt
  - feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/LocationSnoozeProcessor.kt
  - feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/ReminderProcessorBroadcastReceiver.kt
  - feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/SimulatedRemindersRepository.kt
- description: Overview, medicine, reminder, tag, analysis, export and settings screens.
  paths:
  - feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/
  - feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/medicine/
  - feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/statistics/
  - feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/exporters/
  - feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/preferences/
  - feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/AppOptionsMenu.kt
  - feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/AppOptionsViewModel.kt
  - feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/TagFilterViewModel.kt
  - feature/ui/src/main/res/xml/
  - feature/ui/src/main/res/navigation/
- description: English strings and arrays naming the product's words.
  paths:
  - core/ui/src/main/res/values/
- description: README, use cases, reminder flow and glossary.
  paths:
  - README.md
  - docs/UseCases.md
  - docs/reminder_flow.md
  - CONTEXT.md
exclusions:
- description: Build, Gradle, CI, lint and quality tooling configuration.
  paths:
  - build.gradle.kts
  - settings.gradle.kts
  - gradle/
  - .github/
  - .qlty/
  - .sonarlint/
  - lint.xml
  - CodeStyle.xml
- description: Unit, instrumented and fuzz tests.
  paths:
  - app/src/test/
  - app/src/androidTest/
- description: Store listings, screenshots and release scripts.
  paths:
  - fastlane/
  - screenshots.sh
  - uploadToPlay.sh
- description: Database migration schemas.
  paths:
  - core/database/schemas/
- description: Shared design components, formatters, themes and icons.
  paths:
  - core/ui/src/main/java/
  - core/ui/src/main/res/drawable/
- description: Architecture decisions, implementation plans and contributor guidelines.
  paths:
  - docs/adr/
  - docs/superpowers/
  - docs/guidelines/
  - AGENTS.md
  - CONTRIBUTING.md
- description: Debug-only test data generation.
  paths:
  - app/src/main/java/com/futsch1/medtimer/GenerateTestData.kt
unmapped:
- description: Home screen widgets for next reminders and recent events.
  paths:
  - feature/reminders/src/main/java/com/futsch1/medtimer/feature/reminders/widgets/
- description: App introduction shown on first start.
  paths:
  - app/src/main/java/com/futsch1/medtimer/MedTimerAppIntro.kt
- description: Restoring notifications after reboot, force stop or a time change.
  paths:
  - app/src/main/java/com/futsch1/medtimer/Autostart.kt
  - app/src/main/java/com/futsch1/medtimer/AutostartService.kt
  - app/src/main/java/com/futsch1/medtimer/TimeChangeReceiver.kt
- description: Medicine summary sheet opened from a raised or scheduled dose.
  paths:
  - feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/ShowMedicineSheetDialogFragment.kt
  - feature/ui/src/main/java/com/futsch1/medtimer/feature/ui/overview/ShowMedicineViewModel.kt
limitations: []
---

# Coverage
