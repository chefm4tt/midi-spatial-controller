# DAMP Setup — MIDI Spatial Controller

Step-by-step for driving **Dolby Atmos** panning from a Launchkey 49 through the **Dolby Atmos Music
Panner (DAMP)** plugin, in Logic Pro or Pro Tools. About 15 minutes end to end. Self-contained for
someone with no setup beyond the gear they already own.

> This covers the **DAMP plugin** path. For Logic's *native* 3D Object Panner, see
> [setup-guide-logic.md](setup-guide-logic.md). Assignments are in
> [damp-cc-reference.md](damp-cc-reference.md).

> **Written 2026-03-10, not yet walked through against a live install** — DAMP was never installed
> on the studio Mac. Treat the DAMP UI details as drafted rather than confirmed.

**Prerequisites:** macOS (Apple Silicon or Intel) · Novation Launchkey 49 Mk3 · Logic Pro or Pro
Tools · headphones · a free Dolby Developer account.

Headphones are genuinely enough — binaural monitoring means no speaker rig is required, which is what
makes this reproducible in a dorm room.

## 1 — Install DAMP

The Dolby Atmos Music Panner is free and exposes X / Y / Z / Size as MIDI-learnable controls.

1. Create a free account at `developer.dolby.com`
2. Download the macOS installer
3. Run it — installs **AU** for Logic and **AAX** for Pro Tools
4. In Logic → Preferences → Plug-In Manager, scan for AU plugins and confirm DAMP appears

## 2 — Load the Launchkey preset

The SysEx preset puts encoders 1–4 on CCs 21–24 in custom mode, bypassing InControl's defaults.

1. Get `presets/launchkey-atmos-controller.syx` from the repo
2. Connect the Launchkey over USB
3. Open Novation Components in Chrome or Edge and select the Launchkey 49
4. Import the SysEx and send it to a **user slot — slot 2 or higher**
5. On the device press **Custom** and select that slot

**Confirm before continuing:** wiggle encoder 1 and check Logic's MIDI Monitor shows CC 21 on
channel 1. If it does not, nothing downstream will work and step 3 will look broken for the wrong
reason.

## 3 — Logic Pro

**Enable Atmos:** File → Project Settings → Audio → Spatial Audio = **Dolby Atmos**, then set the
mixer output to the Atmos renderer (binaural for headphones).

**Insert DAMP:** on an Atmos object track, insert slot → Audio Units → Dolby → Atmos Music Panner.

**Bind by MIDI Learn:** right-click **X** → *Learn MIDI CC* → turn encoder 1. Repeat for Y (encoder
2), Z (encoder 3), Size (encoder 4).

**Verify:** play audio, turn the knobs — the ball in the DAMP visualiser moves and the binaural
output shifts in 3D.

**Then save the project as a template.** Bindings live in the project file, so this is what stops you
redoing them every session.

## 4 — Pro Tools

Setup → Session Setup → audio format **Dolby Atmos** (needs an Atmos production licence), insert DAMP
(AAX) on an Atmos object track, then bind exactly as in Logic — the MIDI Learn workflow is identical.
Save a template for the same reason.

## Troubleshooting

**Encoders send the wrong CCs** — InControl is probably still active. Press **Custom** and confirm
you are in the user slot holding the preset, not the default mode. This is the most common failure
and it looks like a broken preset.

**DAMP missing in Logic** — Preferences → Plug-In Manager → *Reset & Rescan All*. If it is still
absent, re-run the installer and check `/Library/Audio/Plug-Ins/Components/`.

**Bindings gone after reopening a project** — expected, not a fault. They are saved *in the project
file*. Open the template saved above; re-learning takes about two minutes.

**Bindings still not responding** — check the MIDI channel. The preset should send on channel 1;
DAMP's MIDI Learn accepts any channel by default, so a mismatch usually points at the Launchkey
config in Novation Components.
