# Logic Pro Setup — MIDI Spatial Controller

Step-by-step for Logic Pro + Novation Launchkey 49. Setup time: ~15 minutes.

---

## Prerequisites

- macOS
- Novation Launchkey 49 (Mk3 or Mk4) + USB cable
- Logic Pro (10.7.5+ recommended)
- Headphones
- SysEx preset loaded on Launchkey (see Step 1)

> **If you already use Custom Slot 4 (Mk3):** back it up before loading our preset. See [backup-restore.md](backup-restore.md).

---

## Step 1 — Load the Launchkey Preset

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

---

## Step 2 — Enable Dolby Atmos in Logic

1. Open Logic Pro and create a new project (or open an existing one)
2. Go to **File** → **Project Settings** → **Audio**
3. Find the **Spatial Audio** dropdown and set it to **Dolby Atmos**
4. Logic will ask you to confirm — click **OK**
5. Logic automatically creates a **Binaural** output in the Mixer for headphone monitoring (no extra setup needed)

---

## Step 3 — Create an Audio Track

You need a track to put audio on. If you already have one, skip to Step 4.

1. Go to **Track** → **New Track** (or press **Option+Cmd+N**)
2. Select **Audio** in the dialog that appears
3. Leave the defaults (mono input is fine) and click **Create**
4. You should see a new audio track in the track list — the channel strip on the left should show an **Atmos** button (purple), which means Logic is routing this track through the Atmos renderer

---

## Step 4 — Open the 3D Object Panner

Logic's built-in **3D Object Panner** is what controls where a sound sits in 3D space. It appears automatically on every Atmos object track.

1. Look at the bottom of the channel strip on the left side — below the volume fader, you'll see a small **surround panner** (it looks like a small square with a dot in it)
2. **Double-click** the surround panner to open the full **3D Object Panner** window
3. You'll see a top-down grid (Front/Back/Left/Right) and a side view (Ear Level/Top), with parameter values at the top:
   - **Left/Right** — horizontal position
   - **Back/Front** — depth position
   - **Elevation** — height position
   - **Size** — how wide/diffuse the sound is
   - **Spread** — (we won't map this one)

---

## Step 5 — Map Encoders to the Panner (Controller Assignments)

Logic's **Controller Assignments** let you map any MIDI CC to any plugin or panner parameter.

1. Make sure your Launchkey encoder custom mode is active:
   - **Mk3:** press **Custom** → select **Slot 4**
   - **Mk4:** hold **Shift** + press **Pad 8** (top row, rightmost)
2. In the 3D Object Panner window, **click the Left/Right value** (the number at the top-left, e.g., 0.000) to select it
3. Press **Cmd+L** — this enters Logic's Controller Assignment Learn mode
4. Turn **encoder 1** on the Launchkey — Logic captures CC 21 and assigns it to Left/Right
5. **Click the Back/Front value**, then turn **encoder 2**
6. **Click the Elevation value**, then turn **encoder 3**
7. **Click the Size value**, then turn **encoder 4**
8. Press **Cmd+L** again to exit Learn mode

All four parameters are now mapped:

| Panner Parameter | Encoder | CC |
|------------------|---------|-----|
| Left/Right | 1 | 21 |
| Back/Front | 2 | 22 |
| Elevation | 3 | 23 |
| Size | 4 | 24 |

---

## Step 6 — Test

1. Drag any audio file from Finder onto the track (or record something — any audio will work)
2. Put on your headphones
3. Press **Play** (spacebar)
4. While audio is playing, slowly turn encoders 1–4 on the Launchkey
5. In the 3D Object Panner window, watch the dot — it should move as you turn the knobs
6. In your headphones, the sound should move left/right (encoder 1), front/back (encoder 2), up/down (encoder 3), and get wider/narrower (encoder 4)

If the sound doesn't move, check the [Troubleshooting](#troubleshooting) table below.

---

## Step 7 — Save as Template

Controller Assignment bindings are stored in the project file. If you close this project without saving, you'll have to redo the mapping step next time.

1. Go to **File** → **Save as Template...**
2. Give it a name (e.g., "Atmos MIDI Controller")
3. Click **Save**

Next time you want to use the spatial controller, open this template instead of starting from scratch — all your encoder mappings will be pre-loaded.

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| Encoders send wrong CCs | Make sure the correct custom slot/mode is active on the Launchkey (not InControl mode) |
| Cmd+L doesn't respond | Click directly on a parameter **value** in the panner window first, then press Cmd+L |
| Sound doesn't move in headphones | Confirm Spatial Audio is set to Dolby Atmos in File → Project Settings → Audio |
| Panner not visible on channel strip | Make sure the track is an Atmos object track (purple Atmos button visible on channel strip) |
| Encoder mappings gone after reopening | Open the template you saved in Step 7 |

---

## CC Reference

| Encoder | CC | Panner Parameter |
|---------|----|------------------|
| 1 | 21 | Left/Right |
| 2 | 22 | Back/Front |
| 3 | 23 | Elevation |
| 4 | 24 | Size |
