---
appliesTo:
- {type: capability, id: restore-backup}
- {type: entity, id: medicine}
- {type: entity, id: reminder-event}
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/futsch1/medtimer/database/backup/JSONMedicineBackup.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/futsch1/medtimer/database/backup/JSONReminderEventBackup.kt
- kind: code
  role: implementation
  target: app/src/main/java/com/futsch1/medtimer/database/backup/BackupManager.kt#BackupManager
---

# Restoring a backup replaces what the backup holds

Restoring replaces all medicines, reminders and tags when the backup holds medicine data, the whole history when it holds event data, and the settings it carries; nothing is merged.
