# Backup & Restore — Novation Launchkey 49 Custom Slot 4

The MIDI Spatial Controller preset loads into **Custom Slot 4** on your Launchkey 49. This guide explains how to back up whatever is already in Slot 4 before loading our preset, and how to restore it afterward.

---

## Do You Need to Back Up?

Open [Novation Components](https://components.novationmusic.com) → connect your Launchkey → click **Custom** on the device view. You'll see four numbered preset slots.

- **Slot 4 is empty?** You're safe to skip this guide. Loading our preset won't affect anything.
- **Slot 4 has a preset you use?** Back it up before proceeding.

Most first-year Full Sail students use InControl mode (Logic/Ableton auto-integration) and leave Custom slots empty — Slot 4 is likely empty.

---

## What About InControl Mode?

**InControl is completely separate from Custom presets.** Loading our SysEx to Custom Slot 4 does not touch InControl, Slots 1–3, or any other Launchkey settings. Your DAW integration is unaffected.

---

## Backup — Export Slot 4

1. Connect Launchkey 49 via USB
2. Open [Novation Components](https://components.novationmusic.com) in Chrome or Edge
3. Select your Launchkey 49 Mk3
4. In the Custom presets view, click **Slot 4** to select it
5. Click **Export** (or right-click Slot 4 → Export)
6. Save the `.syx` file somewhere safe (e.g., `~/Documents/launchkey-backups/`)

---

## Restore — Import Your Backup

1. Open Novation Components → select your Launchkey 49 Mk3
2. Click **Import** → select your saved `.syx` file
3. Send it to **Slot 4**
4. On the Launchkey: press **Custom** → select Slot 4 to verify it loaded

---

## Remove Our Preset (Clean Uninstall)

If you want to clear Slot 4 entirely:

1. Open Novation Components → select your Launchkey 49 Mk3
2. Right-click **Slot 4** → **Reset to Default** (or import your backup if you made one)
3. The slot returns to factory state

Your other slots, InControl mode, and all DAW integrations remain untouched.
