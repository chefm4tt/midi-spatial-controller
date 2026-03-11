# CC Reference — MIDI Spatial Controller

Quick-reference for Novation Launchkey 49 Mk3 → Dolby Atmos Music Panner (DAMP) MIDI mappings.

---

## Encoder Assignments

| Encoder | CC | DAMP Parameter | Description |
|---------|----|----------------|-------------|
| 1 | 21 | X | Left/right azimuth |
| 2 | 22 | Y | Front/back depth |
| 3 | 23 | Z | Elevation (up/down) |
| 4 | 24 | Size | Object spread/width |
| 5–8 | 25–28 | *(reserved)* | Phase 2 |

---

## How to Apply These Bindings

These CCs are sent by the Launchkey when the SysEx preset is active (custom slot — not InControl mode).

Bind them to DAMP using MIDI Learn:
1. Right-click any DAMP parameter
2. Select **Learn MIDI CC**
3. Turn the corresponding encoder

Bindings are saved in the DAW project file. Save a template after first setup.

---

## DAMP Parameters — Reference Ranges

| Parameter | Range | Center/Default |
|-----------|-------|----------------|
| X | -1.0 (full left) to +1.0 (full right) | 0.0 (center) |
| Y | 0 (front) to 1.0 (back) | 0.0 (front) |
| Z | 0 (bottom) to 1.0 (top) | 0.5 (ear level) |
| Size | 0 (point source) to 1.0 (diffuse) | 0.0 |

---

## Notes

- Encoder mode in the preset: **absolute** (not relative). Predictable behavior when switching tracks.
- CC channel: 1 (DAMP MIDI Learn accepts any channel by default)
- To confirm CCs are firing: Logic MIDI Monitor or Pro Tools MIDI Monitor before starting MIDI Learn
