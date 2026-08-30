<div align="center">

# `KARISHMA PREMNATH`

### CONTROL SYSTEMS ▸ INDUSTRIAL AUTOMATION ▸ INSTRUMENTATION

![MS ECE](https://img.shields.io/badge/MS_ECE-Northeastern-C8102E?style=for-the-badge)
![IEEE](https://img.shields.io/badge/Published-IEEE_AIDE_2026-00629B?style=for-the-badge&logo=ieee&logoColor=white)
![Co-op](https://img.shields.io/badge/Open_to-Spring_2027_Co--op-1D9E75?style=for-the-badge)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/karishma-premnath)
[![Email](https://img.shields.io/badge/Email-C5221F?style=flat-square&logo=gmail&logoColor=white)](mailto:premnath.ka@northeastern.edu)
[![DOI](https://img.shields.io/badge/DOI-10.1109%2FAIDE69088.2026.11545113-00629B?style=flat-square)](https://doi.org/10.1109/AIDE69088.2026.11545113)

</div>

---

<div align="center">

**I build control systems end to end** — narrative, instrument index, PLC logic,
and a simulated plant to prove it before anything touches hardware.
Instrumentation background, so I think in **tags, ranges and failure directions**
before I think in code.

</div>

---

## ⬢ &nbsp;Right now

|  |  |
|---|---|
| 🔭 &nbsp;**Building** | **WTS-100**, a two-stage water treatment PLC skid — 4 PID loops, 12 alarms, 8 interlocks, 33 I/O, closed out through 40 test cases |
| 🌱 &nbsp;**Learning** | ladder logic in CODESYS · Gaussian-process models for predictive control · anomaly detection on SCADA time-series |
| 👯 &nbsp;**Open to** | open-source PLC tooling — Structured Text bug detection, OpenPLC/Modbus TCP plant simulators, ISA-5.1 P&ID templates |
| 🤝 &nbsp;**Looking for** | a **Spring 2027 co-op** in controls, automation or instrumentation |

## ⬢ &nbsp;The control problem I solve

A tank level that must hold steady while the inlet flow fights it. The answer is a
**cascade** — the slow loop sets the target for the fast one:

```
                 level SP 1800 mm
                        │
                        ▼
      ┌───────────┐ flow SP  ┌───────────┐      ┌──────────┐      ┌─────────┐
      │  LIC-102  ├─────────►│  FIC-101  ├─────►│ FCV-101  ├─────►│  T-102  │
      │ level PID │          │ flow PID  │      │  valve   │      │  tank   │
      │   outer   │          │   inner   │      └──────────┘      └────┬────┘
      └─────▲─────┘          └─────▲─────┘                             │
            │                      │                                   │
            │                      └────────── FT-101 ─────────────────┤
            │                                   flow                   │
            └───────────────────── LT-102 ──────────────────────────────┘
                                    level
```

The inner loop rejects flow disturbances before they ever reach the level. Below it,
eight interlocks can pull permission from any actuator — and none of them are allowed
to depend on the same device that runs the process.

That last rule is the whole discipline. `LT-102` is a transmitter: it gives a number
and it runs the loop. `LSHH-102` is a switch: it gives yes or no and it protects the
tank. Different hardware, different physics. If the transmitter sticks at 1800 mm
while the tank keeps filling, the switch still stops the inflow.

## ⬢ &nbsp;A signal, end to end

One analog input, from the process to the interlock. This is the layer most software
people skip:

```
   PROCESS          FIELD DEVICE        LOOP           PLC            LOGIC
   ─────────────────────────────────────────────────────────────────────────────
   tank level  ──►  LT-102        ──►  4-20 mA   ──►  %IW2      ──►  LIC-102 PV
   0-2500 mm        hydrostatic        2-wire         raw 0-27648    scaled mm
                    transmitter        loop-powered

                    ▼ fails LOW                                      ▼
                    dead sensor reads empty  ───────────────►  pumps stop,
                                                               heater blocked
```

Range is chosen from the process, not the pipe. `T-102` is 2500 mm tall, so `LT-102`
is ranged `0–2500 mm` — ranging it `0–10000 mm` "to be safe" throws away resolution,
because accuracy is a percentage of span. `FT-101` is ranged `0–50 m³/h` against a
normal flow of 30: headroom to see a surge, not so much that normal running sits
squashed at the bottom of the scale.

Failure direction is chosen too, per tag, and the choices disagree on purpose:

| Tag | Measures | Fails | Because |
|---|---|---|---|
| `TT-102` | temperature | **high** | a dead sensor reads hot → heater switches off |
| `LT-102` | level | **low** | a dead sensor reads empty → pumps stop, heater blocked |

Opposite directions on the same tank. There is no single safe direction — it depends
on what the reading is used for.

## ⬢ &nbsp;33 I/O, counted

```
   ANALOG IN    7   LT-101  LT-102  FT-101  FT-103  TT-102  PT-101  AT-102
                    radar · hydrostatic · magflow · Coriolis · Pt100 · piezo · toroidal

   ANALOG OUT   4   FCV-101 valve · HTR-101 heater · P-103 dosing · P-102 discharge

   DIGITAL IN  14   ESD-01 · LSLL-101 · LSHH-102 · TSHH-102 · ZSO/ZSC-101
                    pump run + overload feedback · HOA · start · stop · ack
                    NC where a broken wire must trip

   DIGITAL OUT  8   2 pump contactors · discharge pump · 2 valves · heater
                    horn · beacon          all fail off, both valves spring closed
```

## ⬢ &nbsp;Batch sequence

```
   ┌──────┐  start,   ┌──────┐  1200 mm  ┌──────┐  setpoint  ┌───────┐
   │ IDLE ├──no trip─►│ FILL ├──────────►│ HEAT ├───held────►│ DRAIN │
   └───▲──┘           └───┬──┘           └───┬──┘            └───┬───┘
       │                  │                  │                   │
       │                  │ timeout 900 s    │ timeout 1800 s    │
       │                  └────────► alarm A-009 ◄───┘           │
       │                                                         │
       └─────────────────────────────────────────────────────────┘
```

## ⬢ &nbsp;Selected work

<table>
<tr>
<th align="left" width="220">Project</th>
<th align="left">What it is</th>
</tr>
<tr>
<td valign="top">

**[WTS-100](https://github.com/karishmapremnath4/wts-100-water-treatment-skid)**
`water treatment skid`

![IEC61131](https://img.shields.io/badge/IEC_61131--3-0B5394?style=flat-square)
![OpenPLC](https://img.shields.io/badge/OpenPLC-E8710A?style=flat-square)
![Modbus](https://img.shields.io/badge/Modbus_TCP-455A64?style=flat-square)
![ISA](https://img.shields.io/badge/ISA--5.1-6A1B9A?style=flat-square)

</td>
<td valign="top">

A complete PLC control system for two-stage water treatment: control narrative,
ISA-5.1 P&ID, instrument index and signal scaling, IEC 61131-3 Structured Text and
ladder, a Modbus TCP plant simulation with HMI and historian, and a factory
acceptance test.

`4 PID loops` `12 alarms` `8 interlocks` `33 I/O` — **14 FAT cases + 26 logic tests**.
Found **6 design defects across the 40**, rectified all 6 to a 100% pass. The safety
block also compiles and runs in OpenPLC.

</td>
</tr>
<tr>
<td valign="top">

**[PLC-ML](https://github.com/karishmapremnath4/plc-st-bug-detector-ml)**
`ST defect detection + repair`

![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=white)
![sklearn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)

</td>
<td valign="top">

Machine learning that finds — and then rule-repairs — logic bugs in Structured Text:
disabled interlocks, wrong setpoints, missing edge detection. The defects that
**compile cleanly and fail on the plant**.

A corpus of `300 ST programs` across `8 defect classes`, automated feature extraction,
decision tree classifier. **81.7% baseline → 100%** on 60 held-out programs, and all
60 single-defect programs repaired. The gain came from fixing the *features*, not the
model.

</td>
</tr>
<tr>
<td valign="top">

**[Publication](https://ieeexplore.ieee.org/document/11545113)**
`IEEE AIDE 2026`

![IEEE](https://img.shields.io/badge/IEEE_Xplore-00629B?style=flat-square&logo=ieee&logoColor=white)

</td>
<td valign="top">

*Model predictive controller design using machine learning models & implementation of
parameter tuning* — validated on a laboratory benchtop temperature control station,
so real closed-loop control on hardware: sensor noise, actuator dynamics, dead time.

4 ML models (KNN, FNN, ridge, decision tree) against 4 conventional identifications
(state-space, transfer function, ARX, Box-Jenkins), across varying tuning parameters.

</td>
</tr>
<tr>
<td valign="top">

**Wearable vitals belt**
`analog signal chain`

![LM324](https://img.shields.io/badge/LM324-455A64?style=flat-square)
![Analog](https://img.shields.io/badge/Signal_conditioning-6A1B9A?style=flat-square)

</td>
<td valign="top">

Heart rate and respiration from a **single** force-sensitive resistor, where
conventional monitoring needs two separate transducers. The work is in the filters,
not the sensor.

I–V amplification calibrated over a 16-point load curve, `0.98–19 N`; a 0.45 Hz active
low-pass for respiration and a 2.5–5 Hz band-pass for the ballistocardiogram.
Evaluated across `48–108 BPM` and `8–23 breaths/min`.

</td>
</tr>
<tr>
<td valign="top">

**RPA capstone**
`workflow automation`

![UiPath](https://img.shields.io/badge/UiPath-FA4616?style=flat-square&logo=uipath&logoColor=white)
![RPA](https://img.shields.io/badge/RPA-455A64?style=flat-square)

</td>
<td valign="top">

Repetitive data generation, email notification and form submission automated in
**UiPath** and orchestrated to run on a schedule.

Same instinct as the PLC work — take the manual, error-prone, repeated task and let
a machine hold the sequence.

</td>
</tr>
</table>

## ⬢ &nbsp;The result I get asked about

Ridge regression beat the feedforward neural network on every error metric, at lower
computational cost:

| Model | ISE | MSE | IAE | ITAE |
|---|---|---|---|---|
| FNN | 0.9401 | 0.0188 | 3.2225 | 36.6548 |
| Transfer function | 0.4880 | 0.0098 | 1.9484 | 14.3488 |
| **Ridge** | **0.2918** | **0.0058** | **1.1103** | **12.2788** |

`69% lower MSE` and `66% lower ITAE` than the neural network. The regularisation
sweep plateaus past λ = 0.5 — which is the actual answer to *"how did you pick your
tuning parameter?"*, and the reason I trust the number.

## ⬢ &nbsp;In progress

Repos go public as each one lands.

- **AST-GP-MPC** — Gaussian-process model predictive control with chance constraints, Bayesian-optimisation tuning and online adaptation. The MATLAB follow-up to the IEEE paper.
- **PLC log reconstruction** — detecting and rebuilding broken PLC/SCADA logs (missing, corrupted, stuck-at) with a Gaussian process and a Transformer, on real plant data.
- **AMR-MPC** — model predictive control for a differential-drive mobile robot.

## ⬢ &nbsp;Where I've worked

|  |  |  |
|---|---|---|
| **Apollo Hospital** | Biomedical Engineering Intern<br>`Jun–Jul 2025` | Maintained 25+ diagnostic instruments across patient care units, where one failed sensor takes a device out of service. Assisted a senior engineer diagnosing 6 through hardware–software interfacing and signal validation; traced recurring connectivity faults and inconsistent signal thresholds on 3 and restored all 3 to operation. |
| **Dalmia Cements** | Process Control & Automation Intern<br>`Jul 2024` | At a cement unit running crushing, pyroprocessing and packing, monitored 10 process parameters on PLC and SCADA/HMI. Traced 10 field instruments across 3 production stages, recording signal type and measurement range for each, and documented 15 process variations with sensor connectivity data — no wiring faults found. |
| **CodeBind Technologies** | Embedded Systems Intern<br>`Jun 2023` | Manual tracking of 6 parking slots took 3 minutes a scan and delayed vehicle entry. Built an automated system with Arduino, IR sensors and embedded C, wiring sensor hardware to control software and an Android app — 10 seconds a scan, an 18× reduction, correct availability on 20 of 23 test runs. |

## ⬢ &nbsp;Capability

```
PLC & CONTROL      IEC 61131-3 (Ladder · Structured Text) · CODESYS · OpenPLC
                   PID and loop tuning · cascade · ratio · Model Predictive Control
INTERFACES         SCADA · HMI · Modbus TCP
INSTRUMENTATION    transducers · instrument index · I/O list · sensor selection
                   and ranging · 4-20 mA loop design · signal conditioning
                   calibration · data acquisition · system identification
STANDARDS          ISA-5.1 (P&ID) · ISA-18.2 (alarm management)
                   Factory Acceptance Test · troubleshooting and commissioning
LANGUAGES          Python · C · Embedded C · Structured Text · SQL
TOOLS              MATLAB · Simulink · LabVIEW · AutoCAD · Arduino IDE · Multisim
AUTOMATION         UiPath (RPA) · Tableau
```

## ⬢ &nbsp;Ask me about

Cascade and ratio control · PID tuning · 4-20 mA loop design · ISA-5.1 P&IDs ·
why a transmitter must never also be the protection device ·
choosing a fail-safe direction · why ridge regression beat the neural network

⚡ &nbsp;**Fun fact** — I got heart rate *and* breathing rate out of one force-sensitive
resistor. Two vital signs, one sensor, all filter design.

---

<div align="center">

**MS Electrical & Computer Engineering** · Northeastern University · GPA 3.834 · *May 2028*
**BTech Electronics & Instrumentation** · SASTRA Deemed University

`Open to Spring 2027 co-op — controls, automation, instrumentation`

[![LinkedIn](https://img.shields.io/badge/Let's_connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/karishma-premnath)
[![Paper](https://img.shields.io/badge/Read_the_paper-00629B?style=for-the-badge&logo=ieee&logoColor=white)](https://ieeexplore.ieee.org/document/11545113)

</div>
