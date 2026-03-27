# MIDI Spatial Controller

A side project for Full Sail Audio Production students. Maps the Novation Launchkey 49's (Mk3 or Mk4) hardware encoders to the X/Y/Z/Size parameters in the Dolby Atmos Music Panner so you can position sound in 3D space in real time during playback. No custom code required.

This isn't tied to coursework. It's extracurricular, built to see what's actually possible with gear and software that's already in everyone's hands. If you have a Launchkey 49, it takes about 15 minutes to set up.

Works in Logic Pro and Pro Tools.

**Setup time:** ~15 minutes
**Required gear:** Novation Launchkey 49 (Mk3 or Mk4), macOS, Logic Pro or Pro Tools, headphones

---

## What's in This Repo

| Path | Contents |
|------|----------|
| `presets/` | Novation Components SysEx preset (send to Custom Slot 4) |
| `docs/setup-guide-logic.md` | Logic Pro setup walkthrough |
| `docs/setup-guide-protools.md` | Pro Tools setup walkthrough |
| `docs/cc-reference.md` | Quick-reference: encoder to DAMP parameter |
| `docs/backup-restore.md` | How to back up your existing Slot 4 preset and restore it |

---

## Before You Start

The preset loads into **Custom Slot 4** on your Launchkey (Mk3) or as a **Custom Mode** (Mk4). Custom presets are completely separate from InControl mode. Your Logic/Ableton integration is unaffected.

**Mk3 — If you already have something in Custom Slot 4:** back it up first using [docs/backup-restore.md](docs/backup-restore.md). Most students leave Custom slots empty since InControl is the default, so Slot 4 is probably free.

**Mk4 — Custom Modes** are named presets you create or upload in Novation Components. Loading our preset won't overwrite anything.

---

## Quick Start

1. **Download DAMP** (requires free Dolby account): [customer.dolby.com](https://customer.dolby.com/content-creation-and-delivery/dolby-atmos-music-panner/). Install AU for Logic or AAX for Pro Tools.
2. **Load the preset** in [Novation Components](https://components.novationmusic.com): import the `.syx` file from `presets/` and send it to **Custom Slot 4** (Mk3) or upload it as a **Custom Mode** (Mk4).
3. **Activate the preset** on the Launchkey:
   - **Mk3:** press **Custom** → select **Slot 4**
   - **Mk4:** hold **Shift** + press **Pad 8** (top row, rightmost) to activate Encoder Custom Mode 4
4. **In your DAW**, add DAMP to an Atmos object track, then MIDI Learn each encoder:
   - Right-click **X** → turn encoder 1
   - Right-click **Y** → turn encoder 2
   - Right-click **Z** → turn encoder 3
   - Right-click **Size** → turn encoder 4
5. Play audio and turn the knobs. Sound moves in 3D.

See the full walkthrough in `docs/` for your DAW.

---

## Why DAMP?

Logic Pro's built-in 3D Object Panner and Pro Tools' native Atmos panner don't accept generic MIDI CC. The Dolby Atmos Music Panner is a free Dolby plugin that does. It exposes all four spatial parameters as MIDI-learnable controls and works in both DAWs.

DAMP is an official Dolby product distributed through the Dolby Developer portal. See the [product page](https://professional.dolby.com/product/dolby-atmos-content-creation/dolby-atmos-music-panner/) for full documentation.

---

## Gear Required

- Novation Launchkey 49 Mk3 or Mk4 (any color)
- macOS (Apple Silicon or Intel)
- Logic Pro or Pro Tools
- Headphones (the binaural renderer handles spatial output, no speaker rig needed)
- Free Dolby Developer account to download DAMP

---

## Uninstall / Restore

To remove the preset and return to your previous state:

1. Open Novation Components and select your Launchkey 49
2. **Mk3:** Right-click **Custom Slot 4** → **Reset to Default**, or import your backup `.syx`
3. **Mk4:** Delete the custom mode from Components
4. Your other slots/modes and InControl mode are untouched

See [docs/backup-restore.md](docs/backup-restore.md) for the full backup/restore walkthrough.

---

## Resources

| Resource | Link | Notes |
|----------|------|-------|
| Dolby Atmos Music Panner (product page) | [professional.dolby.com](https://professional.dolby.com/product/dolby-atmos-content-creation/dolby-atmos-music-panner/) | Official Dolby product page with documentation |
| DAMP download | [customer.dolby.com](https://customer.dolby.com/content-creation-and-delivery/dolby-atmos-music-panner/) | Requires free Dolby account |
| Novation Components | [components.novationmusic.com](https://components.novationmusic.com) | Official Novation browser app for preset management |
