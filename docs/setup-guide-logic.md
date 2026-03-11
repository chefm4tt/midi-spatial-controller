# Logic Pro Setup — MIDI Spatial Controller

Step-by-step for Logic Pro + Novation Launchkey 49 + DAMP. Setup time: ~15 minutes.

---

## Prerequisites

- macOS
- Novation Launchkey 49 Mk3 + USB cable
- Logic Pro (10.7.5+ recommended)
- Headphones
- DAMP installed (see Step 1)
- SysEx preset loaded on Launchkey (see Step 2)

---

## Step 1 — Install DAMP (AU)

1. Go to [developer.dolby.com](https://developer.dolby.com) and create a free account
2. Download the Dolby Atmos Music Panner (DAMP) for macOS
3. Run the installer — DAMP installs as an Audio Unit to `/Library/Audio/Plug-Ins/Components/`
4. Open Logic → Logic Pro menu → Settings → Plug-In Manager → click **Rescan** — confirm Dolby Atmos Music Panner appears

---

## Step 2 — Load Novation Preset

1. Connect Launchkey 49 via USB
2. Open [Novation Components](https://components.novationmusic.com) in Chrome or Edge
3. Select your Launchkey 49 Mk3
4. Click **Import** → select `launchkey-atmos-controller.syx` from the `presets/` folder
5. Send to **user slot 2** (or any slot above the defaults)
6. On the Launchkey: press **Custom** → select your preset slot

**Verify:** In Logic → Window → MIDI Studio (or use the MIDI Monitor plugin on a track), wiggle encoder 1 — you should see CC 21, channel 1.

---

## Step 3 — Enable Atmos in Logic

1. Logic → File → Project Settings → Audio
2. Set **Spatial Audio** to **Dolby Atmos**
3. In the Mixer, add a **Binaural** output for headphone monitoring (Logic auto-configures this when Atmos is enabled)

---

## Step 4 — Add DAMP to a Track

1. Create an audio or instrument track set as an **Atmos audio object** (not bed)
2. In the channel strip, click an insert slot → Audio Units → Dolby → **Atmos Music Panner**
3. DAMP opens — you'll see the X/Y/Z sphere visualizer and the Size knob

---

## Step 5 — MIDI Learn

1. Right-click **X** in DAMP → **Learn MIDI CC** → turn encoder 1 on the Launchkey
2. Right-click **Y** → Learn → turn encoder 2
3. Right-click **Z** → Learn → turn encoder 3
4. Right-click **Size** → Learn → turn encoder 4

DAMP shows the bound CC number next to each parameter after learning.

---

## Step 6 — Test

1. Import any audio to the track (or record a loop)
2. Press play
3. Turn encoders 1–4 slowly
4. Watch the DAMP sphere — the position should move
5. In your headphones (binaural output), the sound should move left/right, front/back, up/down

---

## Step 7 — Save as Template

MIDI Learn bindings are stored in the project file. Save this session as a Logic template (File → Save as Template) so you don't have to re-learn each session.

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| DAMP not in Logic plugin list | Logic → Plug-In Manager → Rescan. If still missing, reinstall DAMP. |
| Encoders send wrong CCs | Press Custom on Launchkey and confirm correct preset slot is active (not InControl) |
| Sound doesn't move in headphones | Check Logic output is set to Binaural in the Atmos renderer |
| MIDI bindings gone after reopening | Open the template you saved in Step 7 |

---

## CC Reference

| Encoder | CC | DAMP Parameter |
|---------|----|----------------|
| 1 | 21 | X (left/right) |
| 2 | 22 | Y (front/back) |
| 3 | 23 | Z (elevation) |
| 4 | 24 | Size (spread) |
