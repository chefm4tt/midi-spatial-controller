# Backup & Restore — Novation Launchkey 49 Custom Preset

The MIDI Spatial Controller preset loads into **Custom Slot 4** (Mk3) or as a **Custom Mode** (Mk4) on your Launchkey 49. This guide explains how to back up your existing preset before loading ours, and how to restore it afterward.

---

## Do You Need to Back Up?

Open [Novation Components](https://components.novationmusic.com) → connect your Launchkey → click **Custom** on the device view.

**Mk3:** You'll see four numbered preset slots. If Slot 4 is empty, you're safe to skip this guide. If it has a preset you use, back it up before proceeding.

**Mk4:** You'll see your Custom Modes list. Loading our preset creates a new custom mode and won't overwrite anything, but you can still export any mode you want to back up.

Most first-year Full Sail students use InControl mode (Logic/Ableton auto-integration) and leave Custom slots/modes at defaults.

---

## What About InControl Mode?

**InControl is completely separate from Custom presets.** Loading our SysEx to Custom Slot 4 does not touch InControl, Slots 1–3, or any other Launchkey settings. Your DAW integration is unaffected.

---

## Backup — Export Slot 4

1. Connect Launchkey 49 via USB
2. Open [Novation Components](https://components.novationmusic.com) in Chrome or Edge
3. Select your Launchkey 49

**Mk3:**

4. In the Custom presets view, click **Slot 4** to select it
5. Click **Export** (or right-click Slot 4 → Export)
6. Save the `.syx` file somewhere safe (e.g., `~/Documents/launchkey-backups/`)

**Mk4:**

4. In Custom Modes, find the mode you want to back up
5. Click the download/export icon to save as `.syx`
6. Save the file somewhere safe

---

## Restore — Import Your Backup

1. Open Novation Components → select your Launchkey 49
2. Click **Import** (Mk3) or **Upload Custom Mode** (Mk4) → select your saved `.syx` file
3. **Mk3:** Send it to **Slot 4**. **Mk4:** Send to Launchkey.
4. On the Launchkey: press **Custom** → select the restored slot/mode to verify it loaded

---

## Remove Our Preset (Clean Uninstall)

If you want to clear Slot 4 entirely:

1. Open Novation Components → select your Launchkey 49
2. **Mk3:** Right-click **Slot 4** → **Reset to Default** (or import your backup)
3. **Mk4:** Delete the custom mode from the Custom Modes list

Your other slots/modes, InControl mode, and all DAW integrations remain untouched.
