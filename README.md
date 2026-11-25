# IHP__OPA0316 — UNSE 316 ECG analog front-end

Open-source analog IP for the IHP Open-Silicon MPW (SG13G2), category **Analog / OPA**.
Low-power (~90 µW) two-stage ECG front-end: capacitively coupled LNA (×100) + band-pass stage (×5),
on-chip current and voltage references, reset for fast start-up, full pad ring and seal ring.

- `doc/` — Datasheet, Specification, TRL self-assessment, `info.json`
- `release/v.1.0.0/` — final GDS (`OPA0316.gds`, top cell `OPA0316`) and LVS netlist (`OPA0316.spice`)
- `OPA0316-main/` — layout, netlists, verification reports and ngspice testbenches

Designed at Universidad Nacional de Santiago del Estero (UNSE), Argentina. License: Apache-2.0.
