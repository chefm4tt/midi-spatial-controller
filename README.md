# 🎛️ MIDI Spatial Controller

A side project for Full Sail Audio Production students. Maps the Novation Launchkey 49's (Mk3 or Mk4) hardware encoders to the spatial parameters in Logic Pro's built-in 3D Object Panner so you can position sound in 3D space in real time during playback. No extra software required.

This isn't tied to coursework. It's extracurricular, built to see what's actually possible with gear and software that's already in everyone's hands. If you have a Launchkey 49, it takes about 15 minutes to set up.

**Setup time:** ~15 minutes
**Required gear:** Novation Launchkey 49 (Mk3 or Mk4), macOS, Logic Pro (10.7.5+), headphones

---

## What's in This Repo

| Path | Contents |
|------|----------|
| `presets/` | Novation Components SysEx preset |
| `docs/setup-guide-logic.md` | Logic Pro setup walkthrough |
| `docs/cc-reference.md` | Quick-reference: encoder to panner parameter mapping |
| `docs/backup-restore.md` | How to back up your existing preset and restore it |

---

## Before You Start

The preset loads into **Custom Slot 4** on your Launchkey (Mk3) or as a **Custom Mode** (Mk4). Custom presets are completely separate from InControl mode. Your Logic/Ableton integration is unaffected.

**Mk3 — If you already have something in Custom Slot 4:** back it up first using [docs/backup-restore.md](docs/backup-restore.md). Most students leave Custom slots empty since InControl is the default, so Slot 4 is probably free.

**Mk4 — Custom Modes** are named presets you create or upload in Novation Components. Loading our preset won't overwrite anything.

---

## Quick Start

1. **Download the preset** from [`presets/launchkey-atmos-controller.syx`](presets/launchkey-atmos-controller.syx) in this repo.
2. **Load the preset** in [Novation Components](https://components.novationmusic.com): import the `.syx` file you downloaded and send it to **Custom Slot 4** (Mk3) or upload it as a **Custom Mode** (Mk4).
3. **Activate the preset** on the Launchkey:
   - **Mk3:** press **Custom** → select **Slot 4**
   - **Mk4:** hold **Shift** + press **Pad 8** (top row, rightmost) to activate Encoder Custom Mode 4
4. **In Logic**, enable Dolby Atmos, create an audio track, open the **3D Object Panner**, and use **Cmd+L** (Controller Assignments) to map each encoder:
   - **Left/Right** → encoder 1
   - **Back/Front** → encoder 2
   - **Elevation** → encoder 3
   - **Size** → encoder 4
5. Play audio and turn the knobs. Sound moves in 3D.

See [docs/setup-guide-logic.md](docs/setup-guide-logic.md) for the full walkthrough.

---

## How It Works

Logic Pro (10.7.5+) includes a built-in Dolby Atmos renderer and a **3D Object Panner** on every Atmos object track. The panner has four spatial parameters (Left/Right, Back/Front, Elevation, Size) that can be mapped to external MIDI controllers using Logic's **Controller Assignments** (Cmd+L).

This project provides a SysEx preset that configures your Launchkey's first four encoders to send specific MIDI CC messages (21-24). Once loaded, you map each encoder to a panner parameter and you're done -- no extra plugins, no Dolby account, no additional software.

---

## Gear Required

- Novation Launchkey 49 Mk3 or Mk4 (any color)
- macOS (Apple Silicon or Intel)
- Logic Pro (10.7.5+)
- Headphones (Logic's binaural renderer handles spatial output, no speaker rig needed)

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
| Novation Components | [components.novationmusic.com](https://components.novationmusic.com) | Browser app for managing Launchkey presets |
| Logic Pro Dolby Atmos guide | [support.apple.com](https://support.apple.com/guide/logicpro/dolby-atmos-mixing-workflows-lgcp8a3c3dd3/mac) | Apple's official Atmos mixing workflow docs |
| 3D Object Panner reference | [support.apple.com](https://support.apple.com/guide/logicpro/3d-object-panner-overview-lgcp4492e120/mac) | Panner parameter reference |
