# MIDI Spatial Controller

Built for Full Sail Audio Production students. I made this for our Dolby Atmos coursework — it maps the hardware encoders on a Novation Launchkey 49 to X/Y/Z/Size in the Dolby Atmos Music Panner (DAMP) plugin, so you can move sound in 3D space in real-time while audio plays. No custom code required.

Works in Logic Pro and Pro Tools.

**Setup time:** ~15 minutes
**Required gear:** Novation Launchkey 49 Mk3, macOS, Logic Pro or Pro Tools, headphones

---

## What's in This Repo

| Path | Contents |
|------|----------|
| `presets/` | Novation Components SysEx preset — load to Custom Slot 4 |
| `docs/setup-guide-logic.md` | Logic Pro setup walkthrough |
| `docs/setup-guide-protools.md` | Pro Tools setup walkthrough |
| `docs/cc-reference.md` | Quick-reference: encoder → DAMP parameter |
| `docs/backup-restore.md` | How to back up your existing Slot 4 preset and restore it |

---

## Before You Start

The preset loads into **Custom Slot 4** on your Launchkey. Custom presets are completely separate from InControl mode — your Logic/Ableton auto-integration is unaffected.

**If you already have something in Custom Slot 4:** back it up first using [docs/backup-restore.md](docs/backup-restore.md). Most students leave Custom slots empty (InControl is the default), so Slot 4 is probably free.

---

## Quick Start

1. **Download DAMP** — free from [developer.dolby.com](https://developer.dolby.com). Install AU (Logic) or AAX (Pro Tools).
2. **Load the preset** — open [Novation Components](https://components.novationmusic.com), import the `.syx` file from `presets/`, send to **Custom Slot 4**.
3. **Activate the preset** — press Custom on the Launchkey, select **Slot 4**.
4. **In your DAW** — add DAMP to an Atmos object track, then MIDI Learn each encoder:
   - Right-click **X** → turn encoder 1
   - Right-click **Y** → turn encoder 2
   - Right-click **Z** → turn encoder 3
   - Right-click **Size** → turn encoder 4
5. **Play audio and turn the knobs** — sound moves in 3D.

See the full walkthrough in `docs/` for your DAW.

---

## Why DAMP?

Logic Pro's built-in 3D Object Panner and Pro Tools' native Atmos panner don't accept generic MIDI CC. DAMP is a free Dolby plugin that does — it exposes all four spatial parameters as MIDI-learnable controls and works in both DAWs.

---

## Gear Required

- Novation Launchkey 49 Mk3 (any color)
- macOS (Apple Silicon or Intel)
- Logic Pro or Pro Tools
- Headphones (binaural renderer handles spatial output — no speaker rig needed)
- Free Dolby Developer account (DAMP download)

---

## Uninstall / Restore

To remove the preset and return to your previous state:

1. Open Novation Components → select your Launchkey 49 Mk3
2. Right-click **Custom Slot 4** → **Reset to Default**, or import your backup `.syx` if you made one
3. That's it — your other slots and InControl mode are untouched

See [docs/backup-restore.md](docs/backup-restore.md) for the full backup/restore walkthrough.
