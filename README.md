# Nishizumi_Profiles (v1.0.0)

Nishizumi_Profiles is a desktop app for iRacing that automatically manages graphics renderer profiles based on your combo (car, track, or series grouping).

It helps you avoid manually editing `rendererDX11*.ini` every time you switch content.

---

## What this app does

- Detects your current combo from iRacing telemetry.
- Saves per-combo renderer INI profiles.
- Applies the correct profile to your active renderer INI.
- Supports **Monitor**, **OpenXR**, and **OpenVR** renderer files.
- Lets you organize profiles by:
  - Car + track
  - Car only
  - Track only
  - SeriesID
  - SeriesID + track

---

## Quick Start (Easy Setup)

If you just want to start quickly, do this:

1. **Open the app** (`Nishizumi_Profiles.py`).
2. On first launch, choose your iRacing folder (usually `Documents/iRacing`).
3. In setup, select:
   - **Renderer**: Monitor, OpenXR, or OpenVR
   - **Profile model/grouping**: Car + track (recommended for most users)
4. Save settings.
5. Start iRacing and just play.

That’s it — the app will manage and apply profiles based on your selected behavior.

---

## Recommended default configuration

For most users:

- **Renderer**: OpenXR (if using VR OpenXR runtime)
- **Grouping**: Car + track
- **Enabled**: Yes
- **Autosave on manual close**: Yes

---

## Basic daily usage

- Launch Nishizumi_Profiles before or while using iRacing (start with your system is best!)
- Select renderer/grouping at top.
- The app monitors sim sessions and updates/applies profiles when needed.
- Use **Refresh list** to see latest saved combos.

If you’re happy with defaults, you do not need to touch advanced options.

---

## Advanced README (All Features)

Use this section if you want full control over every button and option.

### App configuration area

- **Default renderer**: Chooses which active renderer INI file is targeted.
- **Default grouping**: Chooses how profile keys are generated.
- **Change iRacing folder**: Point to another iRacing Documents folder.

### Combo table

Shows known profiles for currently selected renderer + grouping:

- Combo key
- Track / Layout
- Car
- SeriesID
- Enabled
- Autosave
- Last saved timestamp

Selecting a row loads its values in the editor panel.

### Selected combo / manual editor fields

- Track internal
- Track config/layout
- Track display
- Track display short
- Car path
- Car screen
- Car short
- SeriesID

Use these to manually define or fix combo metadata.

### Flags

- **Enabled**: If disabled, profile won’t be auto-applied for that combo.
- **Autosave on manual close**: If enabled, app updates profile when you close sim manually.

### Buttons and what each one does

- **Clear fields**: Resets editor fields.
- **Refresh list**: Reloads settings, manifest, table, and suggestions.
- **Load current sim combo**: Reads combo data from running iRacing.
- **Save/overwrite profile from selected renderer INI**: Saves current active INI as profile for current combo.
- **Apply selected profile to selected renderer INI**: Writes selected profile back to active INI (sim should be closed).
- **Save enabled/autosave flags**: Stores per-combo enabled + autosave settings.
- **Create/refresh global backup**: Updates fallback backup for selected renderer.
- **Restore global backup to selected renderer INI**: Restores backup to active INI.
- **Open current profiles folder**: Opens profile directory in Explorer.
- **Delete selected profile**: Removes one selected profile.
- **Delete ALL profiles**: Removes all saved profiles.

### Automatic monitor behavior

When running, the monitor loop:

1. Detects sim start/stop.
2. Reads current combo from telemetry.
3. Checks matching saved profile.
4. If mismatch is detected, it can trigger safe close/apply flow.
5. On session close, it can autosave depending on combo settings.

### Generated files and storage

Inside your iRacing documents folder, app data is stored in:

- `combo_profiles/app_settings.json`
- `combo_profiles/index.json`
- Per-renderer/per-grouping profile folders and INI copies

A bootstrap path file is also saved in your home directory so the app remembers your selected iRacing folder.

---

## Requirements

- Windows
- Python 3
- iRacing installed
- Dependencies used by script (`PySide6`, `pywin32`, `psutil`, `irsdk`)

---

## Version

Current release documented here: **1.0.0**

