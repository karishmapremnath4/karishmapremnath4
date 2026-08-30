<div align="center">

# Karishma Premnath

**Control Systems · Industrial Automation · Instrumentation**
MS Electrical & Computer Engineering — Northeastern University, Boston

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/karishma-premnath)
[![IEEE Xplore](https://img.shields.io/badge/IEEE_Xplore-00629B?style=for-the-badge&logo=ieee&logoColor=white)](https://ieeexplore.ieee.org/document/11545113)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:premnath.ka@northeastern.edu)

![Open to Co-op](https://img.shields.io/badge/Open_to-Spring_2027_Co--op-1D9E75?style=flat-square)
![Focus](https://img.shields.io/badge/Focus-Controls_·_PLC_·_Instrumentation-37474F?style=flat-square)

</div>

---

I build control systems the way they get built on a job: process narrative first, then
the instrument index and I/O list, then the logic, then a simulated plant to test it
against. My background is Electronics & Instrumentation, so I care about the parts
that are easy to skip — failure directions, separating control from protection, and
testing that tries to break things rather than confirm they work.

---

## `// featured`

<table>
<tr><td width="50%" valign="top">

### [WTS-100 Water Treatment Skid](https://github.com/karishmapremnath4/wts-100-water-treatment-skid)

Complete PLC control system — narrative, ISA-5.1 P&ID, instrument index, IEC 61131-3
code, Modbus TCP plant simulation, HMI, historian, and a factory acceptance test.

```
Control loops      4   cascade level-flow, ratio dosing
Interlocks         8   cause / action / reset defined
Alarms            12   first-out latching, ISA-18.2
I/O signals       33   7 AI · 4 AO · 14 DI · 8 DO
FAT cases         14   14/14 passing
Logic tests       26   26/26 passing
```

Safety block also compiles and runs in **OpenPLC** as Structured Text.

![IEC61131](https://img.shields.io/badge/IEC_61131--3-0B5394?style=flat-square)
![OpenPLC](https://img.shields.io/badge/OpenPLC-E8710A?style=flat-square)
![Modbus](https://img.shields.io/badge/Modbus_TCP-455A64?style=flat-square)
![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=white)

</td><td width="50%" valign="top">

### [PLC-ST Bug Detector](https://github.com/karishmapremnath4/plc-st-bug-detector-ml)

Machine learning that finds and repairs logic bugs in PLC Structured Text — the kind
that compile cleanly and fail on the plant.

```
Dataset          300   generated ST programs
Defect classes     8   interlock drop, setpoint,
                       missing edge detection, …
Baseline       81.7%   12 features
Final          100.0%  16 features, 60 held out
Repair         60/60   rule-based, per defect class
```

Gains came from **fixing the features, not the model** — every classifier plateaued
near 80% until the setpoint value became visible.

![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![ST](https://img.shields.io/badge/Structured_Text-0B5394?style=flat-square)

</td></tr>
</table>

---

## `// publication`

> **Model predictive controller design using machine learning models and implementation of parameter tuning**
> Giri P., Deepana S., **Karishma P.**, Deepika G. P., Venkatesh S., R. Amirtharajan
> *2026 International Conference on Artificial Intelligence and Data Engineering (AIDE)*, Nitte, India, pp. 326–333
> [`10.1109/AIDE69088.2026.11545113`](https://doi.org/10.1109/AIDE69088.2026.11545113)

MPC on a **laboratory benchtop temperature control station** — real closed-loop
control on hardware, not simulation. Four conventional modelling methods compared
against four machine learning models:

| | Method | ISE | MSE | IAE | ITAE |
|---|---|---|---|---|---|
| ML | Feedforward NN | 0.9401 | 0.0188 | 3.2225 | 36.6548 |
| **ML** | **Ridge regression** | **0.2918** | **0.0058** | **1.1103** | **12.2788** |
| Conventional | Transfer function | 0.4880 | 0.0098 | 1.9484 | 14.3488 |
| Conventional | State space | 0.4980 | 0.0108 | 1.9544 | 14.3502 |

Ridge wins on every metric — **69% lower MSE** than the FNN — and costs less to
compute, which is what matters in a real-time loop. Δu_max, R and Q are each swept
independently to show where they stop helping.

Full abstract, figures and results → [`publications`](https://github.com/karishmapremnath4/publications)

---

## `// stack`

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

## `// experience`

**Apollo Hospital** · Biomedical Engineering Intern · Trichy, India · Jun–Jul 2025
Maintained 25+ diagnostic instruments across patient care units. Diagnosed and resolved
6 instruments with a senior engineer through hardware-software interfacing, sensor
connectivity and signal validation. Traced recurring connectivity faults and
inconsistent signal thresholds on 3 devices, restoring all 3 to service.

**Dalmia Cements** · Process Control & Automation Intern · Dalmiapuram, India · Jul 2024
Monitored 10 process parameters through PLC and SCADA/HMI dashboards at a cement unit
running crushing, pyroprocessing and packing. Traced 10 field instruments across 3
production stages, recording signal type and measurement range for each. Documented
15 process variations with sensor connectivity data.

**CodeBind Technologies** · Embedded Systems Intern · Chennai, India · Jun 2023
Built an automated car parking system using Arduino, IR sensors and embedded C with an
Android app. Cut slot-tracking time from 3 minutes to 10 seconds, with correct
availability logged on 20 of 23 test runs.

---

## `// education`

| | | |
|---|---|---|
| **Northeastern University** | MS Electrical & Computer Engineering | Jan 2026 – May 2028 |
| Boston, MA | GPA 3.834 / 4.00 · ML, Robotics | |
| **SASTRA Deemed University** | BTech Electronics & Instrumentation | Oct 2021 – Sept 2025 |
| Thanjavur, India | | |
