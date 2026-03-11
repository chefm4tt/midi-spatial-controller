# MIDI Spatial Controller

Real-time Dolby Atmos spatial control using a Novation Launchkey 49. Maps the hardware encoders to X/Y/Z/Size parameters in the Dolby Atmos Music Panner (DAMP) plugin — works in Logic Pro and Pro Tools with zero custom code.

**Setup time:** ~15 minutes
**Required gear:** Novation Launchkey 49 Mk3, macOS, Logic Pro or Pro Tools, headphones

---

## What's in This Repo

| Path | Contents |
|------|----------|
| `presets/` | Novation Components SysEx preset — load to Launchkey user slot |
| `docs/setup-guide-logic.md` | Logic Pro setup walkthrough |
| `docs/setup-guide-protools.md` | Pro Tools setup walkthrough |
| `docs/cc-reference.md` | Quick-reference: encoder → DAMP parameter |

---

## Quick Start

1. **Download DAMP** — free from [developer.dolby.com](https://developer.dolby.com). Install AU (Logic) and/or AAX (Pro Tools).
2. **Load the preset** — open [Novation Components](https://components.novationmusic.com), import the `.syx` file from `presets/`, send to a user slot on your Launchkey.
3. **Activate the preset** — press Custom on the Launchkey, select your slot.
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
