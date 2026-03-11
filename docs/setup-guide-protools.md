# Pro Tools Setup — MIDI Spatial Controller

Step-by-step for Pro Tools + Novation Launchkey 49 + DAMP. Setup time: ~15 minutes.

---

## Prerequisites

- macOS
- Novation Launchkey 49 Mk3 + USB cable
- Pro Tools (2022.9+ recommended; Atmos requires Ultimate or a Dolby Atmos Production Suite license)
- Headphones
- DAMP installed (see Step 1)
- SysEx preset loaded on Launchkey (see Step 2)

> **If you already use Custom Slot 4:** back it up before loading our preset. See [backup-restore.md](backup-restore.md).

---

## Step 1 — Install DAMP (AAX)

1. Go to [developer.dolby.com](https://developer.dolby.com) and create a free account
2. Download the Dolby Atmos Music Panner (DAMP) for macOS
3. Run the installer — DAMP installs the AAX version for Pro Tools
4. Open Pro Tools — DAMP should appear under Plug-Ins → Multichannel Plug-Ins → Dolby

---

## Step 2 — Load Novation Preset

1. Connect Launchkey 49 via USB
2. Open [Novation Components](https://components.novationmusic.com) in Chrome or Edge
3. Select your Launchkey 49 Mk3
4. Click **Import** → select `launchkey-atmos-controller.syx` from the `presets/` folder
5. Send to **Custom Slot 4**
6. On the Launchkey: press **Custom** → select **Slot 4**

**Verify:** In Pro Tools → Setup → MIDI → MIDI Monitor, wiggle encoder 1 — should show CC 21, channel 1.

---

## Step 3 — Configure Atmos Session

1. File → New Session → select an **Atmos** session template, or
2. Open an existing session → Setup → Session Setup → set Audio Format to **Dolby Atmos**
3. Configure the Atmos Renderer for binaural output (headphones)

---

## Step 4 — Add DAMP to a Track

1. Create an audio track configured as an **Atmos audio object**
2. Click an insert slot on the track → Multichannel Plug-Ins → Dolby → **Atmos Music Panner**
3. DAMP opens — X/Y/Z sphere and Size knob visible

---

## Step 5 — MIDI Learn

1. Right-click **X** in DAMP → **Learn MIDI CC** → turn encoder 1 on the Launchkey
2. Right-click **Y** → Learn → turn encoder 2
3. Right-click **Z** → Learn → turn encoder 3
4. Right-click **Size** → Learn → turn encoder 4

---

## Step 6 — Test

1. Add audio to the track
2. Press play
3. Turn encoders 1–4
4. DAMP sphere should move; sound should move in headphones

---

## Step 7 — Save as Template

Save the session as a Pro Tools session template (File → Save As Template) to preserve MIDI bindings.

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| DAMP not in Pro Tools | Reinstall DAMP; verify AAX path `/Library/Application Support/Avid/Audio/Plug-Ins/` |
| Encoders send wrong CCs | Press Custom on Launchkey, confirm **Slot 4** is active (not InControl) |
| No spatial movement in headphones | Confirm Atmos renderer set to Binaural in session setup |
| MIDI bindings gone after reopening | Open session template saved in Step 7 |

---

## CC Reference

| Encoder | CC | DAMP Parameter |
|---------|----|----------------|
| 1 | 21 | X (left/right) |
| 2 | 22 | Y (front/back) |
| 3 | 23 | Z (elevation) |
| 4 | 24 | Size (spread) |
