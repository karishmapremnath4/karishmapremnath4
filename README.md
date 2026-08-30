<!-- ============================================================
     KARISHMA PREMNATH — GitHub Profile README
     ============================================================ -->

<div align="center">

[![Typing SVG](https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=22&pause=1000&color=1D9E75&center=true&vCenter=true&width=680&lines=Karishma+Premnath;MS+ECE+%40+Northeastern+%7C+Control+Systems+%2B+PLC+%2B+ML;IEEE-published+%E2%80%94+Model+Predictive+Control;Open+to+Co-op+%E2%80%94+Controls+%2F+Automation+%2F+Robotics)](https://git.io/typing-svg)

<br/>

[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/karishma-premnath)
[![IEEE](https://img.shields.io/badge/-IEEE_Xplore-00629B?style=flat-square&logo=ieee&logoColor=white)](https://ieeexplore.ieee.org/document/11545113)
[![Email](https://img.shields.io/badge/-Email-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:premnath.ka@northeastern.edu)

</div>

---

```yaml
# karishma.yml
name:        Karishma Premnath
degree:      M.S. Electrical & Computer Engineering  (GPA 3.834 / 4.00)
university:  Northeastern University, Boston
undergrad:   B.Tech, Electronics & Instrumentation Engineering (SASTRA)
focus:       [ Model Predictive Control, PLC / SCADA, Instrumentation, Machine Learning, Embedded ]
published:   IEEE AIDE 2026  # MPC using machine learning models + parameter tuning
status:      Open to Co-op / Internship — Control Systems, Automation, Robotics
```

---

### `// publication`

**Model predictive controller design using machine learning models & implementation of parameter tuning**
*IEEE AIDE 2026 — Technically Co-Sponsored Conference, NMAM Institute of Technology, Nitte, India · Published in IEEE Xplore*

> Implemented and validated a model predictive controller on a **laboratory temperature control station**,
> evaluating **4 machine learning models** (KNN, feedforward neural network, ridge regression, decision tree)
> against **4 conventional identification methods** (state-space, transfer function, ARX, Box–Jenkins)
> across varying tuning parameters.
>
> **Ridge-based MPC achieved the lowest MSE (0.0058) and ITAE (12.2788)** of the models evaluated —
> a 69% MSE and 66% ITAE improvement over the FNN-based controller.
>
> 🔗 [ieeexplore.ieee.org/document/11545113](https://ieeexplore.ieee.org/document/11545113)

---

### `// projects`

**`ml-mpc-temperature/`** — *Model predictive control with ML plant models + parameter tuning*

The controller behind the IEEE publication above. Built the MPC formulation, identified the plant with
both ML and classical methods, and swept the tuning parameters to compare closed-loop performance on a
laboratory temperature control station. Ridge regression gave the best-tracking model
(**MSE 0.0058, ITAE 12.2788**); the regularisation sweep plateaus past λ = 0.5, which is how the final
tuning was chosen rather than by trial and error alone.

![MATLAB](https://img.shields.io/badge/MATLAB-0076A8?style=flat-square&logo=mathworks&logoColor=white)
![Simulink](https://img.shields.io/badge/Simulink-FF7A00?style=flat-square)
![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=white)
![System ID](https://img.shields.io/badge/System_Identification-37474f?style=flat-square)

---

**`water-treatment-skid/`** — *PLC control system design, ladder + ST, and full FAT* · Aug 2026

Designed and tested a control system for a two-stage water treatment skid: **4 PID loops**
(cascade level–flow and ratio control), **12 alarms**, **8 interlocks** and **33 I/O signals**
(7 AI, 4 AO, 14 DI, 8 DO). Wrote the IEC 61131-3 ladder logic and structured text, a Modbus TCP
plant simulation and the process HMI, then executed **14 FAT cases and 26 logic tests** —
**6 design defects found across 40 test cases, all 6 rectified to a 100% pass**.

![IEC 61131-3](https://img.shields.io/badge/IEC_61131--3-004B87?style=flat-square)
![Structured Text](https://img.shields.io/badge/Structured_Text-1565c0?style=flat-square)
![Modbus TCP](https://img.shields.io/badge/Modbus_TCP-37474f?style=flat-square)
![SCADA/HMI](https://img.shields.io/badge/SCADA%20%2F%20HMI-546e7a?style=flat-square)

---

**`plc-st-bug-detection/`** — *ML-assisted PLC structured text defect detection + rule-based repair* · Jun 2026

Built a dataset of **300 PLC structured text programs** seeded with **8 functional defect classes**
(disabled interlock, incorrect setpoint, and others) — bugs that compile cleanly but fail in operation.
A Python pipeline extracts features straight from the code and a decision tree classifies the defect:
accuracy went from a **81.7% baseline to 100% on 60 held-out programs**, and the rule-based repair
stage corrected **all 60** single-defect programs.

![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![Structured Text](https://img.shields.io/badge/Structured_Text-1565c0?style=flat-square)

---

**`smart-wearable-monitor/`** — *Respiratory + heart rate from one sensor* · May 2024

A wearable belt that recovers **both respiration and heart rate from a single force-sensitive resistor**,
where conventional monitoring needs separate transducers. Built and calibrated the analog chain:
I–V amplification over a **16-point load curve from 0.98 to 19 N**, an LM324 active low-pass filter
(0.45 Hz) for respiration and a band-pass filter (2.5–5 Hz) for the ballistocardiogram. Validated across
**48–108 BPM and 8–23 breaths/min**.

![Embedded C](https://img.shields.io/badge/Embedded_C-00599C?style=flat-square&logo=c&logoColor=white)
![Signal Conditioning](https://img.shields.io/badge/Signal_Conditioning-37474f?style=flat-square)
![Instrumentation](https://img.shields.io/badge/Instrumentation-1565c0?style=flat-square)

---

**`smart-parking-system/`** — *Automated real-time slot tracking* · Jun 2023

Manual tracking of 6 parking slots took 3 minutes per scan and delayed vehicle entry. Built an automated
system with **Arduino, IR sensors and embedded C**, plus an Android app for live slot state — cutting
tracking to **10 seconds (18x faster)**, with correct availability logged on **20 of 23 test runs**.

![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat-square&logo=arduino&logoColor=white)
![Embedded C](https://img.shields.io/badge/Embedded_C-00599C?style=flat-square&logo=c&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?style=flat-square&logo=android&logoColor=white)

---

### `// experience`

```
Apollo Hospital           Biomedical Engineering Intern       (Jun–Jul 2025)
├── Maintained 25+ diagnostic instruments across patient care units
├── Diagnosed 6 instruments with a senior engineer — HW/SW interfacing,
│   sensor connectivity, signal validation
└── Traced recurring connectivity faults and inconsistent signal
    thresholds on 3 devices, restoring all 3 to service

Dalmia Cements            Process Control & Automation Intern (Jul 2024)
├── Monitored 10 process parameters via PLC and SCADA/HMI across
│   crushing, pyroprocessing and cement packing
├── Traced 10 field instruments over 3 production stages, logging
│   signal type and measurement range for each
└── Documented 15 process variations with sensor connectivity data

CodeBind Technologies     Embedded Systems Intern             (Jun 2023)
└── Built the automated car parking system above (Arduino + IR +
    embedded C + Android app)
```

---

### `// stack`

```python
stack = {
  "control"        : ["Model Predictive Control", "PID & loop tuning", "Cascade & ratio control",
                      "System identification"],
  "plc_automation" : ["IEC 61131-3 Ladder", "Structured Text", "SCADA & HMI", "Modbus TCP",
                      "CODESYS", "OpenPLC"],
  "instrumentation": ["Transducers & sensor selection", "4-20 mA loop design", "Instrument index / I-O list",
                      "Signal conditioning & calibration", "Data acquisition",
                      "ISA-5.1 (P&ID)", "ISA-18.2 (alarms)", "FAT & commissioning"],
  "languages"      : ["Python", "C", "Embedded C", "Structured Text", "SQL"],
  "tools"          : ["MATLAB", "Simulink", "LabVIEW", "AutoCAD", "Multisim", "Arduino IDE"],
}
```

---

### `// education`

```
Northeastern University — Boston, MA                  Jan 2026 – Present
└── M.S. Electrical & Computer Engineering            Expected May 2028
    ├── GPA : 3.834 / 4.00
    └── Coursework : Machine Learning, Robotics

SASTRA Deemed University — Thanjavur, India           Oct 2021 – Sept 2025
└── B.Tech, Electronics & Instrumentation Engineering
```

---

<div align="center">

`STATUS: OPEN_TO_WORK` — Control Systems · Automation · Robotics Co-op

[![Connect](https://img.shields.io/badge/Connect%20on%20LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/karishma-premnath)
[![Read the paper](https://img.shields.io/badge/Read%20the%20IEEE%20paper-00629B?style=flat-square&logo=ieee&logoColor=white)](https://ieeexplore.ieee.org/document/11545113)

</div>
