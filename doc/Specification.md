# OPA0316 — Specification

| Item | Target |
|---|---|
| Application | Single-lead ECG / biopotential acquisition, battery powered |
| Supply | 3.3 V single supply, < 100 µW |
| Gain | ×500 ±10 % |
| Bandwidth | 0.5 Hz – 150 Hz (diagnostic ECG band) |
| Input-referred noise | < 5 µVrms (0.5–150 Hz) |
| CMRR | > 90 dB |
| Input range | ±5 mV differential, linear |
| Output | Single-ended, centered at VDD/2, able to drive an external ADC input |
| Start-up | Reset pin to settle the high-value pseudo-resistors in milliseconds |
| Bias | On-chip reference current set by one external resistor |
| Verification | Corners (tt, ss, ff, sf, fs) at 0 / 27 / 50 °C and Monte Carlo (mismatch) at schematic level |
