# EPM-240-8P - Synthetic traction motor datasheet

**OCR benchmark edition 1.0 | 20 tables | Fictional engineering data**

> **Important:** this document is entirely synthetic and intended only for OCR / table-structure benchmarking. It is not a real manufacturer datasheet, is not electrically or mechanically validated, and must not be used for design, procurement, test certification, or wiring.

## Benchmark conventions

- PDF and HTML preserve original merged cells using native `rowspan` / `colspan`.
- In this Markdown edition, every merged cell is expanded by repeating its text into each covered cell. Repeated strings therefore intentionally encode merged regions.
- Multi-row headers remain separate Markdown rows; header-group labels are repeated across their child columns.
- Decimal point is used as decimal separator; thin spaces separate thousands. Parentheses, `±`, `≤`, `≥`, `≈`, Greek symbols, Unicode subscripts/superscripts and SI units are intentional OCR challenges.
- A dash (`—`) means not applicable / not stated, not zero. `∞` means continuous / no imposed time limit in the synthetic test definition.

## Document index

| ID | Table | Columns |
|---|---|---:|
| T01 | General ratings and identification | 6 |
| T02 | Torque-speed operating envelope | 8 |
| T03 | Rated and overload duty points | 7 |
| T04 | Electrical ratings and terminal quantities | 8 |
| T05 | Stator winding and slot / pole layout | 7 |
| T06 | Equivalent-circuit parameters versus temperature | 7 |
| T07 | dq-axis operating map samples | 8 |
| T08 | Back-EMF and air-gap flux harmonics | 6 |
| T09 | Efficiency map - motoring | 7 |
| T10 | Loss breakdown versus speed and load | 8 |
| T11 | Thermal network and temperature limits | 7 |
| T12 | Liquid-cooling circuit characteristics | 8 |
| T13 | Insulation system and dielectric verification | 8 |
| T14 | Mechanical envelope and dimensional tolerances | 8 |
| T15 | Bearing arrangement, fits and lubrication | 6 |
| T16 | Rotor and permanent-magnet material data | 8 |
| T17 | Vibration and acoustic order spectrum | 8 |
| T18 | Control and protection calibration values | 8 |
| T19 | Sensor pinout and signal conditioning | 8 |
| T20 | Environmental, reliability and interface qualification | 8 |

## T01 - General ratings and identification

Nameplate data, rated operating point and declared tolerances

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Property family | Characteristic | Nominal value | Nominal value | Permitted / operating range | Permitted / operating range |
| --- | --- | --- | --- | --- | --- |
| Property family | Characteristic | Value | Unit | Lower | Upper |
| Identification | Machine designation | EPM-240-8P | — | — | — |
| Identification | Frame / revision | 245-L180 / Rev. C.4 | — | — | — |
| Identification | Serial number format | X8-26-000000 | — | — | — |
| Rated output | Continuous mechanical power | 150 | kW | 0 | 150 |
| Rated output | Peak mechanical power | 220 | kW | 0 | 220 |
| Rated output | Rated shaft torque | 238.7 | N·m | 0 | 238.7 |
| Rated output | Rated speed | 6 000 | r/min | 0 | 12 000 |
| Supply | DC-link voltage, U<sub>DC</sub> | 800 | V | 650 | 900 |
| Supply | Number of phases | 3 | — | 3 | 3 |
| Supply | Pole / slot count | 8 / 48 | — | 8 / 48 | 8 / 48 |
| Construction | Cooling / protection | Water-glycol / IP67 | — | — | — |
| Construction | Insulation / thermal class | Class 200 (R) | — | — | — |
| Construction | Approximate mass | 82.0 ± 2.0 | kg | 80.0 | 84.0 |

**Engineering note:** All values are synthetic. “—” denotes not applicable or not specified; it is not a zero value.

## T02 - Torque-speed operating envelope

Motoring and regenerative quadrants; positive speed convention

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Operating mode | Speed region | Speed n | Speed n | Shaft torque T<sub>m</sub> | Shaft torque T<sub>m</sub> | Mechanical power P<sub>m</sub> | Mechanical power P<sub>m</sub> |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Operating mode | Speed region | From | To | Min. | Max. | Min. | Max. |
| Motoring | Constant torque | 0 | 3 000 | 0 | 520 | 0 | 163.4 |
| Motoring | Constant power | 3 000 | 6 000 | 238.7 | 477.5 | 150.0 | 150.0 |
| Motoring | Field weakening | 6 000 | 12 000 | 119.4 | 238.7 | 150.0 | 220.0 |
| Motoring | Overspeed (no load) | 12 000 | 13 200 | 0 | 12 | 0 | 16.6 |
| Regeneration | Continuous regen | 0 | 6 000 | -180 | 0 | -113.1 | 0 |
| Regeneration | Peak regen | 0 | 4 000 | -420 | 0 | -175.9 | 0 |
| Coast / open circuit | All speeds | 0 | 12 000 | ≈ 0 | ≈ 0 | ≈ 0 | ≈ 0 |

**Engineering note:** Peak values are time-limited; simultaneous maximum speed, torque and power are not guaranteed.

## T03 - Rated and overload duty points

Discrete test points for dynamometer setup and thermal-soak checks

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Test block | Point | n [r/min] | T<sub>m</sub> [N·m] | P<sub>m</sub> [kW] | Duration [s] | Duty description |
| --- | --- | --- | --- | --- | --- | --- |
| Continuous | CP-01 | 6 000 | 238.7 | 150.0 | ∞ | S1 reference |
| Continuous | CP-02 | 3 000 | 477.5 | 150.0 | ∞ | Low-speed thermal limit |
| Continuous | CP-03 | 12 000 | 119.4 | 150.0 | ∞ | High-speed field weakening |
| Overload | OL-10 | 2 000 | 520 | 108.9 | 60 | 10 min cycle; 10% duty |
| Overload | OL-30 | 4 000 | 500 | 209.4 | 30 | 30 s pulse; 5 min rest |
| Overload | OL-05 | 8 000 | 262.6 | 220.0 | 5 | Peak-power validation |
| Regenerative | RG-01 | 3 000 | -420 | -131.9 | 20 | DC-link absorption enabled |
| Regenerative | RG-02 | 6 000 | -180 | -113.1 | ∞ | Continuous regen reference |

**Engineering note:** P<sub>m</sub> = 2πnT<sub>m</sub>/60 000. Sign convention: motoring power and torque are positive; generating values are negative.

## T04 - Electrical ratings and terminal quantities

Three-phase quantities; RMS values unless explicitly marked peak

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Quantity group | Parameter | Symbol | Rated | Rated | Short-time / limit | Short-time / limit | Unit |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Quantity group | Parameter | Symbol | Nominal | Tolerance | Maximum | Condition | Unit |
| DC bus | Link voltage | U<sub>DC</sub> | 800 | ± 5 | 900 | V | At inverter terminals |
| DC bus | Undervoltage threshold | U<sub>UV</sub> | 620 | ± 10 | — | — | V |
| DC bus | Overvoltage trip | U<sub>OV</sub> | — | — | 930 | V | Trip, 50 ms debounce |
| AC side | Phase current, continuous | I<sub>ph,rms</sub> | 250 | ± 3% | 250 | A | At 120 °C winding |
| AC side | Phase current, peak | I<sub>ph,pk</sub> | 520 | ± 5% | 520 | A | ≤ 10 s |
| AC side | Fundamental phase voltage | U<sub>ph,1</sub> | 265 | ± 4 | 310 | V | At base speed |
| Frequency | Electrical at 6 000 r/min | f<sub>e</sub> | 400 | ± 1 | — | Hz | p = 4 pole pairs |
| Frequency | Electrical at 12 000 r/min | f<sub>e,max</sub> | 800 | ± 2 | 880 | Hz | Overspeed excluded |
| Power quality | Power factor | cos φ | 0.96 | ± 0.02 | — | — | At rated point |

**Engineering note:** For balanced sinusoidal operation: P<sub>1</sub> = √3 U<sub>LL</sub>I<sub>L</sub>cosφ. “Peak” current is instantaneous phase-current magnitude.

## T05 - Stator winding and slot / pole layout

Geometric winding specification and phase-belt assignment

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Stator section | Feature | Overall | Overall | Phase A | Phase B | Phase C |
| --- | --- | --- | --- | --- | --- | --- |
| Stator section | Feature | Value | Unit | Value | Value | Value |
| Topology | Slot / pole count | 48 / 8 | — | 16 slots | 16 slots | 16 slots |
| Topology | Slots per pole per phase, q | 2 | — | — | — | — |
| Topology | Coil pitch | 5 / 6 | slot | — | — | — |
| Topology | Winding factor, k<sub>w1</sub> | 0.948 | — | — | — | — |
| Conductor | Parallel paths | 2 | — | — | — | — |
| Conductor | Turns per phase, N<sub>ph</sub> | 48 | turn | — | — | — |
| Conductor | Copper area per slot | 18.4 | mm² | — | — | — |
| Insulation | Slot liner thickness | 0.30 | mm | Class 200 | Class 200 | Class 200 |
| Insulation | Phase separation | Double | — | A-B | B-C | C-A |
| Connection | Winding connection | Star (Y) | — | Neutral floating | Neutral floating | Neutral floating |
| Connection | Terminal resistance at 20 °C | R<sub>LL,20</sub> = 18.6 | mΩ | 6.20 mΩ/phase | 6.20 mΩ/phase | 6.20 mΩ/phase |

**Engineering note:** Slot / phase allocation shown as aggregate counts; detailed coil-side numbering is intentionally omitted in this synthetic example.

## T06 - Equivalent-circuit parameters versus temperature

Per-phase fundamental-frequency parameters; star-equivalent values

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Parameter class | Parameter | Symbol | 20 °C | 100 °C | 160 °C | Unit |
| --- | --- | --- | --- | --- | --- | --- |
| Resistance | DC phase resistance | R<sub>s,dc</sub> | 6.20 | 8.15 | 9.62 | mΩ |
| Resistance | AC phase resistance at 400 Hz | R<sub>s,ac</sub> | 7.10 | 9.34 | 11.02 | mΩ |
| Inductance | Direct-axis inductance | L<sub>d</sub> | 0.285 | 0.279 | 0.274 | mH |
| Inductance | Quadrature-axis inductance | L<sub>q</sub> | 0.612 | 0.598 | 0.584 | mH |
| Inductance | Zero-sequence inductance | L<sub>0</sub> | 0.041 | 0.041 | 0.040 | mH |
| Magnetic | PM flux linkage at 25 °C | ψ<sub>PM</sub> | 0.118 | 0.114 | 0.109 | Wb |
| Magnetic | Reluctance saliency ratio | L<sub>q</sub>/L<sub>d</sub> | 2.15 | 2.14 | 2.13 | — |
| Derived | Copper temperature coefficient | α<sub>Cu</sub> | 0.00393 | — | — | K⁻¹ |
| Derived | Time constant at 20 °C | τ = L<sub>d</sub>/R<sub>s</sub> | 46.0 | — | — | ms |

**Engineering note:** Resistance correction: R(T) = R(T₀)[1 + α<sub>Cu</sub>(T − T₀)]. Values are illustrative and do not replace measured parameter identification.

## T07 - dq-axis operating map samples

Selected current vectors for MTPA and field-weakening regions

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Region | Point | n [r/min] | i<sub>d</sub> [A] | i<sub>q</sub> [A] | β [electrical °] | T<sub>e</sub> [N·m] | V<sub>s</sub> [V rms] |
| --- | --- | --- | --- | --- | --- | --- | --- |
| MTPA | M-01 | 500 | -34 | 180 | -79.3 | 168 | 74 |
| MTPA | M-02 | 1 500 | -71 | 320 | -77.5 | 292 | 183 |
| MTPA | M-03 | 3 000 | -112 | 440 | -75.7 | 510 | 262 |
| MTPA | M-04 | 3 000 | -126 | 500 | -75.9 | 520 | 286 |
| Field weakening | FW-01 | 6 000 | -210 | 330 | -122.5 | 239 | 298 |
| Field weakening | FW-02 | 9 000 | -285 | 210 | -143.6 | 171 | 301 |
| Field weakening | FW-03 | 12 000 | -315 | 145 | -157.2 | 119 | 307 |
| Regeneration | RG-03 | 4 000 | -64 | -390 | -99.3 | -402 | 276 |
| Regeneration | RG-04 | 8 000 | -180 | -210 | -130.6 | -178 | 305 |

**Engineering note:** Park convention: i<sub>d</sub> is negative in field weakening. β = atan2(i<sub>q</sub>, i<sub>d</sub>) according to the stated sign convention.

## T08 - Back-EMF and air-gap flux harmonics

Open-circuit line-to-line voltage at 1 000 r/min, 25 °C rotor temperature

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Signal | Component | Order h | Frequency [Hz] | Amplitude [V rms] | Relative level [%] |
| --- | --- | --- | --- | --- | --- |
| E<sub>LL</sub> | Fundamental | 1 | 66.67 | 38.4 | 100.00 |
| E<sub>LL</sub> | 3rd harmonic | 3 | 200.00 | 0.18 | 0.47 |
| E<sub>LL</sub> | 5th harmonic | 5 | 333.33 | 1.12 | 2.92 |
| E<sub>LL</sub> | 7th harmonic | 7 | 466.67 | 0.76 | 1.98 |
| E<sub>LL</sub> | 11th harmonic | 11 | 733.33 | 0.31 | 0.81 |
| Air-gap B<sub>r</sub> | Fundamental peak | 1 | — | 0.82 | 100.00 |
| Air-gap B<sub>r</sub> | 5th spatial harmonic | 5 | — | 0.024 | 2.93 |
| Air-gap B<sub>r</sub> | 7th spatial harmonic | 7 | — | 0.015 | 1.83 |
| THD, line-line | THD = √ΣE<sub>h</sub>²/E<sub>1</sub> | — | — | 3.72 | % |

**Engineering note:** Voltage amplitudes scale approximately with speed under open-circuit conditions; harmonic phase angles are not included.

## T09 - Efficiency map - motoring

η = Pshaft / Pdc; stabilized coolant at 65 °C and UDC = 800 V

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Load torque T/T<sub>rated</sub> | Speed band | Speed band | Speed band | Speed band | Speed band | Speed band |
| --- | --- | --- | --- | --- | --- | --- |
| Load torque T/T<sub>rated</sub> | 1 000 rpm | 2 000 rpm | 4 000 rpm | 6 000 rpm | 8 000 rpm | 12 000 rpm |
| 10 % | 84.1 % | 88.7 % | 90.8 % | 90.1 % | 88.2 % | 82.5 % |
| 20 % | 89.4 % | 92.6 % | 94.8 % | 94.2 % | 92.1 % | 87.0 % |
| 40 % | 92.1 % | 95.0 % | 96.4 % | 96.8 % | 95.6 % | 91.3 % |
| 60 % | 92.8 % | 95.7 % | 96.9 % | 97.1 % | 96.4 % | 92.8 % |
| 80 % | 92.5 % | 95.4 % | 96.8 % | 97.2 % | 96.6 % | 93.0 % |
| 100 % | 91.9 % | 95.0 % | 96.5 % | 97.0 % | 96.1 % | 92.4 % |
| 120 % | 90.2 % | 94.1 % | 95.9 % | 96.2 % | 94.8 % | 90.1 % |
| Measurement status: interpolated grid; cells within ±0.4 percentage points (pp) | Measurement status: interpolated grid; cells within ±0.4 percentage points (pp) | Measurement status: interpolated grid; cells within ±0.4 percentage points (pp) | Measurement status: interpolated grid; cells within ±0.4 percentage points (pp) | Measurement status: interpolated grid; cells within ±0.4 percentage points (pp) | Measurement status: interpolated grid; cells within ±0.4 percentage points (pp) | Measurement status: interpolated grid; cells within ±0.4 percentage points (pp) |

**Engineering note:** Cells are efficiency percentages, not absolute power. Values below 10% torque are excluded from the map.

## T10 - Loss breakdown versus speed and load

Estimated steady-state loss partition at 65 °C inlet coolant

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Load case | n [r/min] | Pout [kW] | Copper losses | Copper losses | Iron losses | Iron losses | Other losses |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Load case | n [r/min] | Pout [kW] | P<sub>Cu</sub> [kW] | Share [%] | P<sub>Fe</sub> [kW] | Share [%] | P<sub>misc</sub> [kW] |
| Low speed | 1 500 | 25.0 | 0.82 | 37.6 | 0.31 | 14.2 | 1.05 |
| Low speed | 2 500 | 65.0 | 1.46 | 42.0 | 0.58 | 16.7 | 1.44 |
| Base speed | 6 000 | 150.0 | 2.05 | 38.0 | 1.24 | 23.0 | 2.11 |
| Base speed | 7 500 | 180.0 | 2.41 | 40.1 | 1.72 | 28.6 | 1.88 |
| High speed | 10 000 | 180.0 | 1.88 | 32.8 | 2.36 | 41.2 | 1.49 |
| High speed | 12 000 | 150.0 | 1.54 | 28.1 | 2.84 | 51.8 | 1.10 |
| Total at rated point / 6 000 r/min | Total at rated point / 6 000 r/min | 150.0 | 2.05 | 38.0 | 1.24 | 23.0 | 2.11 |

**Engineering note:** Other losses include magnet eddy-current, mechanical, stray-load and windage components. Share denominator: total motor loss, not Pout.

## T11 - Thermal network and temperature limits

Lumped thermal nodes used by the supervisory derating model

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Thermal zone | Node / component | C<sub>th</sub> [J/K] | R<sub>th</sub> to coolant [K/W] | Continuous limit [°C] | Transient limit [°C] | Sensor tag |
| --- | --- | --- | --- | --- | --- | --- |
| Stator | Copper hot spot | 2 850 | 0.036 | 180 | 200 / 10 s | NTC-W1 |
| Stator | Slot liner | 1 220 | 0.052 | 155 | 180 / 60 s | NTC-S2 |
| Stator | Stator yoke | 4 600 | 0.028 | 150 | 165 / 60 s | NTC-S3 |
| Rotor | Permanent magnet | 1 480 | 0.091 | 150 | 165 / 5 s | EST-R1 |
| Rotor | Rotor core | 3 200 | 0.074 | 180 | 200 / 10 s | EST-R2 |
| Rotor | Shaft | 1 050 | 0.063 | 160 | 180 / 60 s | — |
| Coolant | Inlet manifold | — | — | 65 | 75 / 30 s | NTC-CI |
| Coolant | Outlet manifold | — | — | 85 | 95 / 10 s | NTC-CO |

**Engineering note:** R<sub>th</sub> values are equivalent fitted values for the synthetic thermal model; they are not directly additive across parallel heat paths.

## T12 - Liquid-cooling circuit characteristics

Water / ethylene-glycol mixture 50:50 by volume; nominal inlet 65 °C

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Circuit segment | Quantity | Nominal | Nominal | Nominal | Minimum | Maximum | Acceptance / note |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Circuit segment | Quantity | Symbol | Value | Unit | Value | Value | Acceptance / note |
| Pump | Volumetric flow | Q̇ | 12.0 | L/min | 8.0 | 16.0 | No air entrainment |
| Pump | Inlet pressure | p<sub>in</sub> | 180 | kPa(g) | 120 | 250 | kPa(g) |
| Pump | Coolant inlet temperature | T<sub>in</sub> | 65 | °C | −20 | 80 | °C |
| Motor jacket | Pressure drop at 12 L/min | Δp<sub>m</sub> | 24 | kPa | 18 | 35 | kPa |
| Motor jacket | Wetted volume | V<sub>m</sub> | 0.82 | L | 0.75 | 0.90 | L |
| Connections | Inlet port | G 3/8 | — | — | — | — | ISO 228-1 |
| Connections | Outlet port | G 3/8 | — | — | — | — | ISO 228-1 |
| Connections | Leak test | p<sub>test</sub> | 300 | kPa | — | — | 60 s; ≤ 1 cm³/min |

**Engineering note:** Coolant properties assumed at 65 °C: ρ = 1 045 kg/m³; c<sub>p</sub> = 3.55 kJ/(kg·K); λ = 0.41 W/(m·K).

## T13 - Insulation system and dielectric verification

Production and type-test requirements; values are synthetic targets

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Test family | Test item | Applied quantity | Applied quantity | Duration | Pass criterion | Pass criterion | Test reference |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Test family | Test item | Value | Unit | Duration | Value | Unit | Test reference |
| Insulation resistance | Phase-to-frame | U<sub>test</sub> = 1 000 | V DC | 60 | ≥ 100 | MΩ | IEC 60034-1* |
| Insulation resistance | After humidity conditioning | 500 | V DC | 60 | ≥ 20 | MΩ | Internal WI-EL-07 |
| Insulation resistance | Polarization index, PI | R<sub>10 min</sub>/R<sub>1 min</sub> | — | — | ≥ 2.0 | — | IEEE 43* |
| Withstand voltage | Stator to frame | 2.4 | kV AC rms | 60 | No breakdown | — | IEC 60034-1* |
| Withstand voltage | Repetitive impulse | V<sub>pk</sub> = 1.8 | kV | 10⁶ pulses | No partial discharge above 10 pC | — | Internal WI-EL-12 |
| Partial discharge | Apparent charge | q<sub>PD</sub> ≤ 10 | pC | — | ≤ 10 | pC | IEC 60270* |
| Insulation material | Thermal class | 200 (R) | — | — | — | — | IEC 60085* |

**Engineering note:** Asterisk (*) identifies a reference family only; verify the current edition and applicability before certification or compliance claims.

## T14 - Mechanical envelope and dimensional tolerances

All dimensions in mm unless otherwise indicated; datum A = shaft axis

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Feature group | Feature / datum | Nominal | Upper dev. | Lower dev. | Inspection tool | Geometric control | Geometric control |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Feature group | Feature / datum | Nominal | Upper dev. | Lower dev. | Inspection tool | Tolerance | Reference |
| Housing | Outer diameter ØD | 245.00 | +0.10 | −0.10 | CMM | 0.08 | A |
| Housing | Overall length L | 312.0 | +0.5 | −0.5 | Height gauge | 0.20 | B |
| Housing | Mounting foot width | 82.0 | +0.2 | −0.2 | Caliper | 0.15 | A-B |
| Housing | Pilot diameter ØP | 160.00 | +0.02 | 0.00 | Air gauge | 0.015 | A |
| Shaft | Shaft extension Ød | 45.000 | 0.000 | −0.016 | Micrometer | 0.008 | A |
| Shaft | Keyway width b | 14.00 | +0.018 | 0.000 | Gauge blocks | 0.02 | A |
| Shaft | Runout at bearing seat | — | — | — | Dial indicator | 0.010 | A |
| Shaft | Threaded end | M36 × 1.5-6g | — | — | Thread ring | Class 6g | ISO metric |
| Air gap | Radial air gap δ | 0.90 | +0.08 | −0.08 | Feeler / CMM | 0.05 | A |
| Air gap | Concentricity rotor/stator | — | — | — | CMM | Ø0.04 | A |

**Engineering note:** Do not infer a manufacturing tolerance from a nominal-only dimension. “—” means no separate tolerance is specified in this table.

## T15 - Bearing arrangement, fits and lubrication

Drive-end (DE) and non-drive-end (NDE) assembly data

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Assembly end | Component | Designation / value | Fit / clearance | Lubricant | Service data |
| --- | --- | --- | --- | --- | --- |
| DE | Deep-groove bearing | 6209-C3 | k5 / H6 | Polyurea NLGI-2 | Sealed for life |
| DE | Bore / OD | 45 / 85 mm | k5 / H6 | — | Radial load ≤ 4.2 kN |
| DE | Dynamic / static rating | 35.1 / 21.6 kN | — | — | C / C₀ |
| DE | Reference life L₁₀h | ≥ 30 000 h | — | — | n = 6 000 r/min |
| NDE | Cylindrical roller bearing | NU208-E | j5 / H6 | Polyurea NLGI-2 | Sealed for life |
| NDE | Bore / OD | 40 / 80 mm | j5 / H6 | — | Axial float 0.4-0.7 mm |
| NDE | Grease temperature | T₍g,max₎ = 150 °C | — | — | Peak 10 min |
| Assembly | Axial preload (DE) | 80 ± 15 N | — | — | Shim controlled; axial |
| Assembly | End-play at 20 °C | 0.05-0.12 mm | — | — | Axial, assembled |

**Engineering note:** Bearing life estimate follows L₁₀ = (C/P)ᵖ × 10⁶ revolutions; p = 3 for ball bearings and 10/3 for roller bearings.

## T16 - Rotor and permanent-magnet material data

Nominal supplier-grade properties; magnetic data at stated test conditions

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Material zone | Property | Symbol | Value | Unit | Test temperature [°C] | Tolerance / class | Remark |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Permanent magnet | Grade | — | N42SH | — | 20 | SH | Sintered NdFeB |
| Permanent magnet | Remanence | B<sub>r</sub> | 1.30-1.34 | T | 20 | ± 0.02 T | Along easy axis |
| Permanent magnet | Intrinsic coercivity | H<sub>cj</sub> | ≥ 1 592 | kA/m | 20 | Minimum | Hcj |
| Permanent magnet | Reversible coefficient | α<sub>Br</sub> | −0.11 | %/K | 20-120 | Typical | Reversible |
| Rotor core | Steel grade | — | 35PN230 | — | 20 | M270-like | Lamination |
| Rotor core | Density | ρ | 7 650 | kg/m³ | 20 | ± 2% | Nominal |
| Rotor core | Electrical resistivity | ρ<sub>e</sub> | 4.7 × 10⁻⁷ | Ω·m | 20 | ± 10% | Longitudinal |
| Shaft | Steel grade | — | 42CrMo4 QT | — | 20 | EN 10083 | Quenched / tempered |
| Shaft | Yield strength | R<sub>p0.2</sub> | ≥ 750 | MPa | 20 | Minimum | Axial specimen |

**Engineering note:** Material names and values are illustrative. Supplier certificates and batch traceability override this synthetic table.

## T17 - Vibration and acoustic order spectrum

Radial acceleration measured at housing, DE horizontal axis; no-load sweep

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Speed band | Order | Frequency relation | Amplitude a<sub>rms</sub> | Amplitude a<sub>rms</sub> | Limit | Limit | Evaluation |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Speed band | Order | Frequency relation | Value | Unit | Value | Unit | Evaluation |
| 0-3 000 | 1× | n/60 | 0.42 | mm/s | 1.8 | mm/s | RMS, 10 Hz HPF |
| 0-3 000 | 2× | 2n/60 | 0.18 | mm/s | 1.0 | mm/s | RMS |
| 0-3 000 | 48× slot pass | 48n/60 | 0.09 | mm/s | 0.60 | mm/s | Order tracking |
| 3 000-8 000 | 1× | n/60 | 0.61 | mm/s | 2.2 | mm/s | 10 s dwell |
| 3 000-8 000 | 2× | 2n/60 | 0.24 | mm/s | 1.2 | mm/s | 10 s dwell |
| 8 000-12 000 | 1× | n/60 | 0.88 | mm/s | 2.8 | mm/s | 5 s dwell |
| 8 000-12 000 | Electrical tone at 800 Hz | 12× f<sub>e</sub> | 9.6 | m/s² | 15 | m/s² | FFT, Hanning |
| All speeds | Sound pressure level | L<sub>pA</sub> | 68.5 | dB(A) | 72 | dB(A) | 1 m, hemi-anechoic |

**Engineering note:** The 48× slot-pass label denotes a mechanical order referenced to rotor speed; electrical orders are separately referenced to f<sub>e</sub>.

## T18 - Control and protection calibration values

FOC current loops, speed loop, modulation and fault thresholds

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Control block | Setting | Symbol | Nominal | Min. | Max. | Unit | Activation / qualifier |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Current loop | d-axis bandwidth | f<sub>ci,d</sub> | 1 200 | 800 | 1 500 | Hz | Small-signal, 20 °C |
| Current loop | q-axis bandwidth | f<sub>ci,q</sub> | 1 000 | 700 | 1 300 | Hz | Small-signal |
| Current loop | Current limit | I<sub>lim</sub> | 520 | 0 | 520 | A peak | 10 s maximum |
| Current loop | PWM frequency | f<sub>PWM</sub> | 10 | 8 | 16 | kHz | Center-aligned SVPWM |
| Speed loop | Bandwidth | f<sub>ω</sub> | 18 | 10 | 25 | Hz | No load inertia J = 0.042 kg·m² |
| Speed loop | Overspeed trip | n<sub>trip</sub> | 13 500 | 13 000 | 14 000 | r/min | 100 ms persistence |
| Speed loop | Speed ramp | dn/dt | 2 500 | 500 | 4 000 | r/min/s | Thermal derating may reduce |
| Protection | Winding warning | T<sub>warn</sub> | 160 | 140 | 175 | °C | Derate begins |
| Protection | Winding shutdown | T<sub>trip</sub> | 185 | 175 | 195 | °C | Latch; restart inhibited |
| Protection | DC overvoltage | U<sub>OV</sub> | 930 | 910 | 950 | V | 20 ms debounce |
| Protection | Resolver loss | Δθ<sub>err</sub> | > 12 | — | — | ° | Fault after 50 ms |

**Engineering note:** Controller settings are illustrative calibration values, not validated safety limits. Actual protection requires system-level hazard analysis.

## T19 - Sensor pinout and signal conditioning

Connector X3, 12-way; pin numbers are cavity identifiers

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Connector | Pin | Signal name | Direction | Electrical level | Electrical level | Scaling / calibration | Diagnostic |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Connector | Pin | Signal name | Direction | Range | Nominal | Scaling / calibration | Diagnostic |
| Resolver | 1 | EXC+ | Output | 7.0 | V rms | 10 kHz ± 0.5% | Amplitude check |
| Resolver | 2 | EXC− | Output | 7.0 | V rms | Differential | Short detection |
| Resolver | 3 | SIN+ | Input | 0.5-3.5 | V diff | k = 0.50 V/V | Open / short |
| Resolver | 4 | SIN− | Input | 0.5-3.5 | V diff | Offset < 20 mV | Open / short |
| Resolver | 5 | COS+ | Input | 0.5-3.5 | V diff | k = 0.50 V/V | Open / short |
| Resolver | 6 | COS− | Input | 0.5-3.5 | V diff | Offset < 20 mV | Open / short |
| Temperature | 7 | NTC-W1 | Input | 0-5 | V | R25 = 10 kΩ; B = 3 980 K | Range check |
| Temperature | 8 | NTC-CI | Input | 0-5 | V | R25 = 10 kΩ; B = 3 430 K | Range check |
| Temperature | 9 | NTC-CO | Input | 0-5 | V | R25 = 10 kΩ; B = 3 430 K | Range check |
| Supply / shield | 10 | +5V_S | Output | 4.85-5.15 | V DC | ≤ 60 mA | Overcurrent |
| Supply / shield | 11 | AGND | Return | — | — | Star-ground | Continuity |
| Supply / shield | 12 | SHIELD | Chassis | — | — | 360° clamp | Bond resistance < 10 mΩ |

**Engineering note:** Do not connect resolver excitation pins to the 5 V sensor supply. Pin mapping is fictional and must not be used for hardware wiring.

## T20 - Environmental, reliability and interface qualification

Synthetic qualification matrix; status codes apply to this sample revision only

**Structure note:** original PDF/HTML contains merged header or body cells; Markdown repeats merged-cell contents across the expanded grid.

| Qualification group | Test / interface | Condition | Condition | Exposure / cycles | Acceptance criterion | Sample size n | Status |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Qualification group | Test / interface | Value | Unit | Exposure / cycles | Acceptance criterion | Sample size n | Status |
| Environment | Operating ambient | −40 to +85 | °C | Continuous | Functional operation | 5 | PASS |
| Environment | Thermal cycling | −40 ↔ +150 | °C | 500 cycles | No cracks; insulation drift ≤ 5% | 3 | PASS |
| Environment | Humidity storage | 85 / 85 | %RH / °C | 1 000 h | No corrosion | 3 | PASS |
| Environment | Ingress protection | IP67 | — | 1 m / 30 min | No water ingress | 3 | PASS |
| Mechanical | Random vibration | 10-2 000 | Hz; 12.5 g rms | 8 h / axis | No structural cracks | 3 | PASS |
| Mechanical | Shock | 50 | g; 11 ms | 18 pulses | No functional damage | 3 | PASS |
| Mechanical | Overspeed proof | 15 000 | r/min | 2 min | No permanent deformation | 2 | PASS |
| Reliability | Target service life | 15 000 | h | — | B10 ≥ 12 000 h | — | TARGET |
| Reliability | Weibull shape β | 1.65 | — | — | Estimated β parameter | 10 | EST. |
| Reliability | Field return target | ≤ 50 | ppm | per annum | ≤ 50 ppm/year | — | TARGET |
| Interfaces | HV connector | HVP800-2P | — | 800 V DC; 350 A cont. | Rated interface | — | RELEASED |
| Interfaces | LV connector | X3-12 | — | 12-way sealed | IP67 | — | RELEASED |
| Interfaces | Communication | CAN FD | 2 Mbit/s | data rate | ISO 11898-1* | — | RELEASED |

**Engineering note:** Status legend: PASS = sample met the stated criterion; TARGET = engineering target; EST. = estimated, not demonstrated. All qualification data are fictional.
