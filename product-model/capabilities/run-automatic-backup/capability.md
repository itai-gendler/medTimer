---
availability:
- {place: android-app}
references:
- kind: code
  role: implementation
  target: app/src/main/java/com/futsch1/medtimer/database/backup/BackupManager.kt#BackupManager
- kind: code
  role: implementation
  target: app/src/main/java/com/futsch1/medtimer/AppOptionsActionsImpl.kt#AppOptionsActionsImpl
---

# Run automatic backup

When the app is opened and the chosen interval has passed since the last automatic backup, the Product writes a full backup to the chosen folder.
