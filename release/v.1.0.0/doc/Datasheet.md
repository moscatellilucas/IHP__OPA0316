# OPA0316 (UNSE 316) — Low-power ECG analog front-end

Universidad Nacional de Santiago del Estero (UNSE), Argentina — Electronic Engineering program.
Designer: Lucas Moscatelli. Process: IHP SG13G2 (3.3 V devices `sg13_hv_nmos` / `sg13_hv_pmos`, MIM capacitors, `rhigh` / `rppd` resistors).

## Description
Two-stage analog front-end for single-lead ECG acquisition:
- **Stage 1 (LNA):** capacitively coupled instrumentation amplifier with pseudo-resistor DC feedback, gain ×100.
- **Stage 2 (BPF):** inverting band-pass amplifier, gain ×5 (C1/C2), upper corner set by OTA bandwidth (~150 Hz).
- **On-chip bias:** beta-multiplier current reference (external `Rset`) and mid-supply reference (`rhigh` divider + follower).
- **Fast-settling reset:** T-switches on the pseudo-resistors, controlled by the `rst` pin.
- Output buffer, ten pads (IHP `sg13g2_io` analog/power pads), seal ring, UNSE logo in TopMetal2.

## Main figures (schematic level, ngspice)
| Parameter | Value |
|---|---|
| Supply (VDD) | 3.3 V |
| Output common mode (vref) | 1.65 V |
| Total gain | ~×500 (54 dB) |
| Band | ~0.4–1 Hz to ~150 Hz |
| Input-referred noise (0.5–150 Hz, stage 1) | 3.98–4.86 µVrms over corners |
| CMRR (stage 1) | ~117 dB |
| Linear input range | up to 5 mV ECG (≈2.5 Vpp at output) |
| Supply current | ~25–29 µA (≈90 µW) over corners 0–50 °C |
| External components | `Rset` = 130 kΩ to vss |
| Die (seal ring) | 1.377 mm × 0.980 mm |

## Pinout
| Pad | Side | Function |
|---|---|---|
| inp, inn | top | ECG differential inputs (to electrodes, AC coupled internally) |
| out | bottom | Analog output, centered on vref |
| vref | bottom | 1.65 V internal reference (for decoupling / ADC reference) |
| rst | bottom | Reset (high = fast settling of the pseudo-resistors); keep low in operation |
| rset | bottom | External bias resistor (130 kΩ to vss) |
| vdd, vss | bottom | Core supply 3.3 V / ground |
| iovdd, iovss | left | Pad ring (ESD) supply / ground |

## Verification status (release v.1.0.0)
- DRC: full deck with density — 0 errors; minimal precheck — pass.
- LVS: pass with the default IHP deck options (tap extraction on), 206 = 206 devices.
- Seal ring and fillers included (no-fill window over the logo).
- Not yet done: parasitic extraction (PEX) and post-layout simulation.
