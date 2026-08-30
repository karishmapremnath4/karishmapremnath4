<!-- ============================================================
     KARISHMA PREMNATH — GitHub Profile README
     github.com/karishmapremnath4
     ============================================================ -->

<table>
<tr>
<td width="270" align="center" valign="top">

<img src="assets/karishma.jpg" width="200" alt="Karishma Premnath" />

<a href="https://github.com/karishmapremnath4"><img src="https://readme-typing-svg.demolab.com?font=Inter&weight=800&size=22&duration=2600&pause=900&color=1D9E75&center=true&vCenter=true&width=250&height=40&lines=Karishma+Premnath" alt="Karishma Premnath" /></a>

<b>MS ECE @ NEU</b>

<img src="https://img.shields.io/badge/Control_Systems-1D9E75?style=flat-square" /><br/>
<img src="https://img.shields.io/badge/PLC_%2F_SCADA-0A66C2?style=flat-square" /><br/>
<img src="https://img.shields.io/badge/Embedded-00599C?style=flat-square" /><br/>
<img src="https://img.shields.io/badge/Robotics-FF7A00?style=flat-square" /><br/>
<img src="https://img.shields.io/badge/Machine_Learning-F7931E?style=flat-square" />

</td>
<td valign="top">

<a href="https://github.com/karishmapremnath4"><img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=19&duration=3200&pause=900&color=1D9E75&width=560&height=38&lines=I+build+control+systems%2C+then+test+them+until+they+break.;M.S.+ECE+%40+Northeastern+%C2%B7+Boston%2C+MA;IEEE-published+%E2%80%94+MPC+on+real+hardware;Open+to+Spring+2027+Co-op" alt="tagline" /></a>

My background is **Electronics & Instrumentation** — the field side of automation:
transducers, 4-20 mA loops, sensor ranging, calibration. I'm now doing an
**M.S. in ECE at Northeastern** (GPA 3.834), working across PLC programming,
process control and machine learning.

The through-line: a control system isn't finished when it compiles. It's finished
when someone has tried to make it fail and written down what happened — which is
why most projects below end in a test count, not a demo.

[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/karishma-premnath)
[![IEEE](https://img.shields.io/badge/-IEEE_Xplore-00629B?style=flat-square&logo=ieee&logoColor=white)](https://ieeexplore.ieee.org/document/11545113)
[![Email](https://img.shields.io/badge/-Email-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:premnath.ka@northeastern.edu)
![Location](https://img.shields.io/badge/Boston,_MA-37474f?style=flat-square)

</td>
</tr>
</table>

---

```yaml
# karishma.yml
name:        Karishma Premnath
degree:      M.S. Electrical & Computer Engineering   (GPA 3.834 / 4.00)
university:  Northeastern University, Boston          (Jan 2026 – May 2028)
undergrad:   B.Tech, Electronics & Instrumentation Engineering (SASTRA)
focus:       [ Control Systems, PLC, Machine Learning, Embedded, Robotics ]
published:   IEEE AIDE 2026   # ML-based Model Predictive Control
standards:   [ IEC 61131-3, ISA-5.1, ISA-18.2, FAT ]
status:      Open to Spring 2027 Co-op — Control Systems, Robotics, Automation, PLC
```

---

### `// publication`

**Model Predictive Controller Design using Machine Learning Models & Implementation of Parameter Tuning**
*IEEE AIDE 2026 — Technically Co-Sponsored Conference, NMAM Institute of Technology, Nitte, India* 📄

> Implemented and validated a model predictive controller on a **laboratory temperature
> control station** — real closed-loop control on hardware, with sensor noise, actuator
> dynamics and dead time. Evaluated **4 machine learning models** (KNN, feedforward neural
> network, ridge regression, decision tree) against **4 conventional identification methods**
> (state-space, transfer function, ARX, Box-Jenkins) across varying tuning parameters.
>
> **Ridge-based MPC achieved the lowest MSE (0.0058) and ITAE (12.2788)** among the evaluated
> models — a 69% MSE reduction against the neural network, at lower computational cost.
>
> 🔗 [ieeexplore.ieee.org/document/11545113](https://ieeexplore.ieee.org/document/11545113)

---

### `// projects`

**`water-treatment-skid/`** — *Full PLC control system: design → code → FAT* &nbsp;`Aug 2026`

A complete control-system package for a **two-stage water treatment skid**. Specified
**4 PID loops** (a cascade level–flow pair and a ratio pair), **12 ISA-18.2 alarms**,
**8 interlocks** and **33 I/O signals** (7 AI, 4 AO, 14 DI, 8 DO), documented on an
**ISA-5.1 P&ID** with fail-safe directions for every loop. Implemented in **IEC 61131-3** —
Ladder Diagram for safety and motor control, Structured Text for analog conditioning,
PID and sequencing — driving a first-principles plant simulator over **Modbus TCP** with
an operator HMI and live trending.

**Tested it properly:** executed **14 FAT cases and 26 logic tests**, found **6 design
defects across the 40 cases**, and rectified all 6 to a clean 40/40 pass. Every interlock
tripped and was recorded.

![Ladder](https://img.shields.io/badge/Ladder_Diagram-0A66C2?style=flat-square)
![Structured Text](https://img.shields.io/badge/Structured_Text-1D9E75?style=flat-square)
![CODESYS](https://img.shields.io/badge/CODESYS-EE7203?style=flat-square)
![OpenPLC](https://img.shields.io/badge/OpenPLC-37474f?style=flat-square)
![Modbus TCP](https://img.shields.io/badge/Modbus_TCP-546e7a?style=flat-square)
![ISA-5.1](https://img.shields.io/badge/ISA--5.1_%2F_18.2-795548?style=flat-square)

> ⚠️ The plant is simulated. The control system, documentation and FAT are complete deliverables.

---

**`plc-st-bug-detection/`** — *ML that finds logic bugs a compiler can't* &nbsp;`Jun 2026`

Built a dataset of **300 PLC Structured Text programs** carrying **8 functional defect
classes** — disabled interlocks, incorrect setpoints and similar — the kind that **compile
successfully and still fail during operation**. Wrote a Python workflow for automated
feature extraction from the code, then trained a decision tree to predict which functional
error is present.

Classification accuracy went from an **81.7% baseline to 100% on 60 held-out programs**,
and the rule-based repair pass **rectified all 60 single-defect programs**.

![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=white)
![Structured Text](https://img.shields.io/badge/Structured_Text-1D9E75?style=flat-square)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![Static Analysis](https://img.shields.io/badge/Static_Analysis-37474f?style=flat-square)

---

**`ml-mpc-temperature/`** — *Predictive controller design + ML tuning strategies*

Designed and evaluated a model predictive controller incorporating **4 ML methods** — KNN,
feedforward neural network, ridge regression and decision tree — against 4 conventional
identification methods, under varying tuning parameters. Ridge-based MPC delivered the best
control performance (**MSE 0.0058, ITAE 12.2788**). *(Basis for the IEEE publication above.)*

![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=white)
![MATLAB](https://img.shields.io/badge/MATLAB-0076A8?style=flat-square&logo=mathworks&logoColor=white)
![Simulink](https://img.shields.io/badge/Simulink-FF7A00?style=flat-square)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)

---

**`smart-wearable-monitor/`** — *Dual respiratory + heart-rate wearable (single sensor)* &nbsp;`May 2024`

A wearable belt that monitors **both heart rate and respiratory rate from a single
force-sensitive resistor**, replacing the two transducers conventional monitors need.
Implemented and calibrated the analog chain with I–V amplification across a **16-point load
curve from 0.98 to 19 N**, and an LM324 **active low-pass filter (0.45 Hz)** for respiration
plus a **band-pass filter (2.5–5 Hz)** for the ballistocardiogram — evaluated within
**48–108 BPM** and **8–23 breaths/min**.

![Embedded C](https://img.shields.io/badge/Embedded_C-00599C?style=flat-square&logo=c&logoColor=white)
![Analog Design](https://img.shields.io/badge/Analog_Signal_Chain-37474f?style=flat-square)
![Sensors](https://img.shields.io/badge/Biomedical_Sensors-1565c0?style=flat-square)

---

**`smart-parking-system/`** — *Automated real-time car-parking system* &nbsp;`Jun 2023`

Manual tracking of 6 parking slots took 3 minutes per scan and caused delays at entry.
Designed and deployed an automated system using **Arduino, IR sensors and embedded C**,
with control software and an Android app for live slot tracking. Cut tracking time to
**10 seconds — an 18× reduction — with correct availability logged on 20 of 23 test runs**.

![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat-square&logo=arduino&logoColor=white)
![Embedded C](https://img.shields.io/badge/Embedded_C-00599C?style=flat-square&logo=c&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?style=flat-square&logo=android&logoColor=white)

---

**`rpa-uipath-capstone/`** — *Workflow automation with UiPath*

Automated repetitive data-generation, email-notification and form-submission tasks using
**UiPath**, orchestrated for scheduled, error-free process automation.

![UiPath](https://img.shields.io/badge/UiPath-FA4616?style=flat-square&logo=uipath&logoColor=white)
![RPA](https://img.shields.io/badge/RPA-37474f?style=flat-square)

---

### `// currently building`

```
amr-mpc/         Differential-drive MPC for an autonomous mobile robot      [ in progress ]
ast-gp-mpc/      GP-model MPC with chance constraints + Bayesian tuning     [ in progress ]
plc-datalog-ml/  Reconstructing corrupted PLC/SCADA logs (GP + Transformer) [ in progress ]
```

---

### `// experience`

```
Apollo Hospital           Biomedical Engineering Intern       Jun – Jul 2025
                          Trichy, Tamil Nadu, India
├── Maintained and serviced 25+ diagnostic instruments across patient care units,
│   where one failed sensor takes a device out of service
├── Assisted a senior engineer in diagnosing and resolving 6 medical instruments
│   through hardware-software interfacing, sensor connectivity and signal validation
└── Identified recurring hardware connectivity issues and inconsistent signal
    thresholds for 3 medical devices, restoring all 3 to operation

Dalmia Cements            Process Control & Automation Intern      Jul 2024
                          Dalmiapuram, Tamil Nadu, India
├── At a cement production unit running crushing, pyroprocessing and packing,
│   monitored 10 process parameters through PLC and SCADA/HMI dashboards
├── Traced 10 field instruments across 3 production stages, recording signal
│   type and measurement range for each
└── Documented 15 process variations alongside sensor connectivity data,
    with no wiring faults found

CodeBind Technologies     Embedded Systems Intern                  Jun 2023
                          Chennai, Tamil Nadu, India
└── Built the automated car-parking system above (Arduino + IR + embedded C)
```

---

### `// stack`

```python
stack = {
  "control_automation" : ["PLC programming (IEC 61131-3: Ladder, Structured Text)",
                          "PID & loop tuning", "Cascade & ratio control",
                          "Model Predictive Control", "SCADA & HMI", "Modbus TCP"],

  "instrumentation"    : ["Transducers", "Instrument index & I/O list",
                          "Sensor selection & ranging", "4-20 mA loop design",
                          "Signal conditioning & calibration", "Data acquisition",
                          "System identification", "ISA-5.1 (P&ID)",
                          "ISA-18.2 (alarm management)", "Commissioning", "FAT"],

  "languages"          : ["Python", "C", "Embedded C", "Structured Text", "SQL"],

  "tools"              : ["CODESYS", "OpenPLC", "MATLAB", "Simulink", "LabVIEW",
                          "AutoCAD", "Multisim", "Arduino IDE", "UiPath"],
}
```

---

### `// education`

```
Northeastern University — Boston, MA
└── M.S. Electrical & Computer Engineering          Jan 2026 – Expected May 2028
    ├── GPA : 3.834 / 4.00
    └── Coursework : Machine Learning, Robotics

SASTRA Deemed University — Thanjavur, Tamil Nadu, India
└── B.Tech, Electronics & Instrumentation Engineering    Oct 2021 – Sept 2025
```

---

<div align="center">

`STATUS: OPEN_TO_WORK` — Spring 2027 Co-op · Control Systems · Automation · Robotics

[![Connect](https://img.shields.io/badge/Connect%20on%20LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/karishma-premnath)
[![Read the paper](https://img.shields.io/badge/Read%20the%20IEEE%20paper-00629B?style=flat-square&logo=ieee&logoColor=white)](https://ieeexplore.ieee.org/document/11545113)

</div>
