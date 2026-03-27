# CC Reference — MIDI Spatial Controller

Quick-reference for Novation Launchkey 49 → Logic Pro 3D Object Panner MIDI mappings.

---

## Encoder Assignments

| Encoder | CC | Panner Parameter | Description |
|---------|----|------------------|-------------|
| 1 | 21 | Left/Right | Horizontal position |
| 2 | 22 | Back/Front | Depth position |
| 3 | 23 | Elevation | Height (up/down) |
| 4 | 24 | Size | Object spread/width |
| 5-8 | 25-28 | *(reserved)* | Future use |

---

## How to Apply These Bindings

These CCs are sent by the Launchkey when the SysEx preset is active:

- **Mk3:** Custom Slot 4 (not InControl mode)
- **Mk4:** Encoder Custom Mode 4 (Shift + Pad 8)

Map them to Logic's 3D Object Panner using Controller Assignments:
1. Open the **3D Object Panner** on your track (double-click the surround panner at the bottom of the channel strip)
2. Click a parameter value (e.g., **Left/Right**)
3. Press **Cmd+L** to enter Learn mode
4. Turn the corresponding encoder on the Launchkey
5. Repeat for each parameter, then press **Cmd+L** to exit Learn mode

Bindings are saved in the Logic project file. Save a template after first setup.

---

## Panner Parameters — Reference Ranges

| Parameter | Range | Default |
|-----------|-------|---------|
| Left/Right | -1.0 (full left) to +1.0 (full right) | 0.0 (center) |
| Back/Front | -1.0 (back) to +1.0 (front) | +1.0 (front) |
| Elevation | 0 (ear level) to +1.0 (top) | 0.0 (ear level) |
| Size | 0 (point source) to +90 (diffuse) | 0 |

---

## Notes

- Encoder mode in the preset: **absolute** (not relative). Predictable behavior when switching tracks.
- CC channel: **1**
- To confirm CCs are firing: record-arm an instrument track, record while turning encoders, then check the Event List (**Cmd+7**) for CC 21-24 on channel 1
