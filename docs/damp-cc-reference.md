# CC Reference — Dolby Atmos Music Panner (DAMP)

Encoder-to-CC assignments for driving the **Dolby Atmos Music Panner** plugin from a Novation
Launchkey 49, and the design choices behind them.

> This is the **DAMP plugin** variant. For Logic's *native* 3D Object Panner, see
> [cc-reference.md](cc-reference.md). The two use different CCs and do not conflict — see the last
> section.

> **Drafted 2026-03-10, not yet verified against the plugin.** The DAMP parameter names below came
> from documentation, not from the MIDI Learn interface. Confirm them before treating this as
> canonical.

---

## DAMP spatial parameters

| Parameter | Meaning | Range |
|---|---|---|
| X | left/right azimuth | −1.0 → +1.0 |
| Y | front/back depth | 0 → 1.0 |
| Z | elevation | 0 → 1.0 |
| Size | object spread | 0 → 1.0, point source to diffuse |

## Encoders — CCs 21–28

CCs 21–28 are the Launchkey 49 Mk3 defaults in custom mode.

| Encoder | CC | Parameter |
|---|---|---|
| 1 | 21 | X — primary pan axis |
| 2 | 22 | Y — depth |
| 3 | 23 | Z — height |
| 4 | 24 | Size — spread |
| 5–8 | 25–28 | reserved — LFE send or a second object, Phase 2 |

Faders (CCs 41–49) and pads are entirely Phase 2. Pads would give spatial-position snapshots —
front centre, overhead, rear left — but that needs Scripter MIDI FX or a template approach, so it
is deferred rather than designed.

## MIDI Learn is the whole binding mechanism

**DAMP has no hardcoded CC assignments.** Every binding is made by hand:

1. Right-click the parameter (say **X**) in the DAMP UI
2. Choose **Learn MIDI CC**
3. Turn the target encoder
4. DAMP binds that CC

Repeat for Y, Z and Size.

**Bindings persist in the DAW project file, not in DAMP globally.** That is the single most
important consequence on this page: there is no "set it up once on this machine". Every project
needs the bindings, which is why the setup guide says to save them into a template project rather
than redoing them per session.

## Three design choices worth not reversing

**Absolute encoder mode, not relative.** Set in Novation Components. Absolute gives predictable
behaviour when switching tracks — the jump position is simply the last CC value sent. Relative mode
drifts against a parameter the plugin may have moved independently.

**Save to a dedicated user slot and activate it explicitly.** InControl's default CCs can overlap
the custom preset's, so relying on whatever is loaded invites a collision that presents as an
encoder moving the wrong parameter.

**The same SysEx preset works in both DAWs.** Only the MIDI Learn bindings are per-project, so
cross-DAW portability costs nothing at the hardware layer.

## A confusion worth pre-empting

**Logic's own 3D Object Panner uses CC 25 for azimuth and CC 26 for elevation** in its native MIDI
Learn. That is irrelevant to DAMP and does not conflict with this map — but if someone mixes the two
approaches, those two CCs will appear to do two things at once. Knowing why is easier than debugging
it.
