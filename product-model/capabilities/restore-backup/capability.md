---
availability:
- {place: android-app}
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/futsch1/medtimer/database/backup/BackupManager.kt#BackupManager
- kind: code
  role: implementation
  target: app/src/main/java/com/futsch1/medtimer/database/backup/JSONMedicineBackup.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/futsch1/medtimer/database/backup/JSONReminderEventBackup.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/futsch1/medtimer/database/backup/JSONSettingsBackup.kt
---

# Restore backup

The User restores a backup file, which replaces the medicines, the events, or both, that it contains and applies its settings.
