# Logic Pro Setup — MIDI Spatial Controller

Step-by-step for Logic Pro + Novation Launchkey 49 + DAMP. Setup time: ~15 minutes.

---

## Prerequisites

- macOS
- Novation Launchkey 49 (Mk3 or Mk4) + USB cable
- Logic Pro (10.7.5+ recommended)
- Headphones
- DAMP installed (see Step 1)
- SysEx preset loaded on Launchkey (see Step 2)

> **If you already use Custom Slot 4:** back it up before loading our preset. See [backup-restore.md](backup-restore.md).

---

## Step 1 — Install DAMP (AU)

1. Go to [customer.dolby.com](https://customer.dolby.com/content-creation-and-delivery/dolby-atmos-music-panner/) and create a free account (or sign in if you already have one)
2. Click **Select files for download** → select **Dolby Atmos Music Panner 1.2.0_5965809.dmg** → click **Download**
3. Open the `.dmg` and run the installer — DAMP installs as an Audio Unit to `/Library/Audio/Plug-Ins/Components/`
4. Open Logic → Logic Pro menu → Settings → Plug-In Manager → click **Rescan** — confirm Dolby Atmos Music Panner appears

---

## Step 2 — Load Novation Preset

1. Download `launchkey-atmos-controller.syx` from the [`presets/`](../presets/) folder in this repo (click the file → click **Download** or **Raw**)
2. Connect Launchkey 49 via USB
3. Open [Novation Components](https://components.novationmusic.com) in Chrome or Edge
4. Select your Launchkey 49

**Mk3:**

5. Click **Import** → select the `launchkey-atmos-controller.syx` file you downloaded
6. Send to **Custom Slot 4**
7. On the Launchkey: press **Custom** → select **Slot 4**

**Mk4:**

5. Go to **Custom Modes** → click **Upload Custom Mode** → select the `launchkey-atmos-controller.syx` file you downloaded
6. Click **Send to Launchkey MK4** → select slot **4**
7. On the Launchkey: hold **Shift** + press **Pad 8** (top row, rightmost) to activate Encoder Custom Mode 4

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
| Encoders send wrong CCs | Press Custom on Launchkey and confirm the correct slot/mode is active (not InControl) |
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
