<div align="center">

<img src="https://raw.githubusercontent.com/karishmapremnath4/wts-100-water-treatment-skid/main/drawings/pid.png" width="100%" alt="WTS-100 P&ID"/>

<sub>*ISA-5.1 P&ID — WTS-100 water treatment skid, drawn as part of [this project](https://github.com/karishmapremnath4/wts-100-water-treatment-skid)*</sub>

<br/>

# Karishma Premnath

### Control Systems · Industrial Automation · Instrumentation

**MS Electrical & Computer Engineering** — Northeastern University, Boston
**BTech Electronics & Instrumentation** — SASTRA Deemed University

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/karishma-premnath)
[![IEEE](https://img.shields.io/badge/IEEE_Xplore-00629B?style=for-the-badge&logo=ieee&logoColor=white)](https://ieeexplore.ieee.org/document/11545113)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:premnath.ka@northeastern.edu)

![Open to Spring 2027 Co-op](https://img.shields.io/badge/●_Open_to-Spring_2027_Co--op-1D9E75?style=flat-square&labelColor=0D1117)

</div>

<br/>

> I build control systems the way they get built on a job — process narrative first,
> then the instrument index and I/O list, then the logic, then a simulated plant to
> test against. My background is instrumentation, so I care about what's easy to skip:
> failure directions, keeping control separate from protection, and testing that tries
> to break things instead of confirming they work.

<br/>

<div align="center">

|  |  |  |  |  |
|:-:|:-:|:-:|:-:|:-:|
| **4** | **8** | **12** | **33** | **40** |
| control loops | interlocks | alarms | I/O signals | tests, all passing |

</div>

---

<div align="center">

## WTS-100 Water Treatment Skid

**[`karishmapremnath4/wts-100-water-treatment-skid`](https://github.com/karishmapremnath4/wts-100-water-treatment-skid)**

</div>

A complete PLC control system, documented and tested end to end.

<table>
<tr>
<td width="55%" valign="top">

```
DELIVERABLES
  control narrative       process behaviour, modes, sequence
  instrument index        33 signals, ranges, failure direction
  signal scaling          4-20 mA to engineering units
  ISA-5.1 P&ID            the drawing above
  IEC 61131-3             Structured Text + ladder, 4 POUs
  plant simulation        Modbus TCP, HMI, historian
  factory acceptance test 14 cases, expected vs actual

CONTROL
  LIC-102 ──cascade──> FIC-101    level to flow
  TIC-102                          temperature
  FFIC-103                         dosing, ratio
  sequence     IDLE → FILL → HEAT → DRAIN

VERIFIED
  FAT           14 / 14   ✓
  ladder logic  26 / 26   ✓
  OpenPLC       safety block compiles and runs
```

</td>
<td width="45%" valign="top">

<img src="https://raw.githubusercontent.com/karishmapremnath4/wts-100-water-treatment-skid/main/drawings/ladder_safety.png" width="100%" alt="Safety ladder"/>

<sub>*POU_SAFETY — 6 rungs of interlocks and permissives, IEC 61131-3 Ladder Diagram*</sub>

</td>
</tr>
</table>

![IEC 61131-3](https://img.shields.io/badge/IEC_61131--3-0B5394?style=flat-square)
![Structured Text](https://img.shields.io/badge/Structured_Text-0B5394?style=flat-square)
![Ladder](https://img.shields.io/badge/Ladder_Diagram-0B5394?style=flat-square)
![OpenPLC](https://img.shields.io/badge/OpenPLC-E8710A?style=flat-square)
![Modbus TCP](https://img.shields.io/badge/Modbus_TCP-455A64?style=flat-square)
![ISA-5.1](https://img.shields.io/badge/ISA--5.1-6A1B9A?style=flat-square)
![ISA-18.2](https://img.shields.io/badge/ISA--18.2-6A1B9A?style=flat-square)
![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=white)

---

<div align="center">

## ML-Assisted PLC Bug Detection

**[`karishmapremnath4/plc-st-bug-detector-ml`](https://github.com/karishmapremnath4/plc-st-bug-detector-ml)**

</div>

Machine learning that finds and repairs logic bugs in Structured Text — the kind that
compile cleanly and fail on the plant.

```
    12 features  ──>  81.7%    all models plateau near 80%
                              THRESHOLD_OFF = 0%, features can't see setpoint values
    14 features  ──>  85.0%    + max_real / min_real      THRESHOLD_OFF   0% → 100%
    15 features  ──>  90.0%    + n_estop_uses             INTERLOCK_DROP 50% → 100%
    16 features  ──> 100.0%    + n_dotq                   EDGE_MISS cleared

    repair       ──>   60/60   rule-based fix per defect class
```

The lesson is the diagnosis, not the number: every classifier stalled around 80% until
the *features* could see the setpoint value. The repo says plainly why 100% on
synthetic single-fault code is easier than real plant code.

![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![Structured Text](https://img.shields.io/badge/Structured_Text-0B5394?style=flat-square)

---

<div align="center">

## Publication · IEEE AIDE 2026

</div>

> **Model predictive controller design using machine learning models and implementation of parameter tuning**
> Giri P., Deepana S., **Karishma P.**, Deepika G. P., Venkatesh S., R. Amirtharajan
> *International Conference on Artificial Intelligence and Data Engineering (AIDE)*, Nitte, India, pp. 326–333
> [`10.1109/AIDE69088.2026.11545113`](https://doi.org/10.1109/AIDE69088.2026.11545113)

MPC validated on a **laboratory benchtop temperature control station** — real
closed-loop control on hardware. Four conventional modelling methods against four
machine learning models:

<div align="center">

| Model | ISE | MSE | IAE | ITAE |
|---|--:|--:|--:|--:|
| Feedforward NN | 0.9401 | 0.0188 | 3.2225 | 36.6548 |
| **Ridge regression** | **0.2918** | **0.0058** | **1.1103** | **12.2788** |
| Transfer function | 0.4880 | 0.0098 | 1.9484 | 14.3488 |
| State space | 0.4980 | 0.0108 | 1.9544 | 14.3502 |

</div>

Ridge wins on every metric — **69% lower MSE** than the neural network — and costs
less to compute, which is what decides it for a real-time loop. Δu_max, R and Q are
swept independently to show where each stops helping.

Abstract, figures and full results → **[`publications`](https://github.com/karishmapremnath4/publications)**

---

<div align="center">

## Stack

</div>

```yaml
control_automation:
  plc:        [ IEC 61131-3 Ladder, Structured Text, CODESYS, OpenPLC ]
  control:    [ PID & loop tuning, cascade, ratio, Model Predictive Control ]
  interfaces: [ SCADA, HMI, Modbus TCP ]

instrumentation:
  design:     [ instrument index, I/O list, sensor selection & ranging ]
  signals:    [ 4-20 mA loop design, signal conditioning, calibration, DAQ ]
  standards:  [ ISA-5.1 (P&ID), ISA-18.2 (alarm management) ]
  commission: [ troubleshooting, Factory Acceptance Test ]

programming:
  languages:  [ Python, C, Embedded C, Structured Text, SQL ]
  tools:      [ MATLAB, Simulink, LabVIEW, AutoCAD, Arduino IDE, Multisim ]
```

---

<div align="center">

## Experience

</div>

**Apollo Hospital** — Biomedical Engineering Intern · Trichy, India · `Jun–Jul 2025`
Maintained 25+ diagnostic instruments across patient care units. Diagnosed and resolved
6 instruments with a senior engineer through hardware-software interfacing, sensor
connectivity and signal validation. Traced recurring connectivity faults and
inconsistent signal thresholds on 3 devices, restoring all 3 to service.

**Dalmia Cements** — Process Control & Automation Intern · Dalmiapuram, India · `Jul 2024`
Monitored 10 process parameters through PLC and SCADA/HMI dashboards at a cement unit
running crushing, pyroprocessing and packing. Traced 10 field instruments across 3
production stages, recording signal type and range for each. Documented 15 process
variations with sensor connectivity data.

**CodeBind Technologies** — Embedded Systems Intern · Chennai, India · `Jun 2023`
Built an automated car parking system with Arduino, IR sensors and embedded C plus an
Android app. Cut slot-tracking time from 3 minutes to 10 seconds, with correct
availability logged on 20 of 23 test runs.

---

<div align="center">

<sub>Northeastern University · GPA 3.834 / 4.00 · Jan 2026 – May 2028</sub>

**Open to Spring 2027 co-op — controls, automation, instrumentation.**

[![LinkedIn](https://img.shields.io/badge/Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/karishma-premnath)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:premnath.ka@northeastern.edu)

</div>
