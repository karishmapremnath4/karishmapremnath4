<div align="center">

# Karishma Premnath

**MS Electrical & Computer Engineering, Northeastern University**
Control systems · PLC & industrial automation · Instrumentation

[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/karishma-premnath)
[![IEEE Xplore](https://img.shields.io/badge/-IEEE_Xplore-00629B?style=flat-square&logo=ieee&logoColor=white)](https://ieeexplore.ieee.org/document/11545113)
[![Email](https://img.shields.io/badge/-Email-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:premnath.ka@northeastern.edu)

`Open to Spring 2027 Co-op` — Controls · Automation · Instrumentation

</div>

---

I come from an Electronics & Instrumentation background and I build control systems
end to end: the process narrative and instrument index first, then the PLC logic,
then a simulated plant to test it against. I care about the parts that are easy to
skip — failure directions, interlock design, and testing that actually tries to break
things.

Published in IEEE AIDE 2026 on machine-learning model predictive control, validated
on a laboratory temperature control station.

---

## Repositories

### [wts-100-water-treatment-skid](https://github.com/karishmapremnath4/wts-100-water-treatment-skid)
**A full PLC control system for a two-stage water treatment skid.**

Control narrative, instrument index and signal scaling, an ISA-5.1 P&ID, IEC 61131-3
Structured Text and ladder, a Modbus TCP plant simulation, an HMI and a historian.
4 control loops (cascade level-flow, ratio dosing), 8 interlocks, 12 alarms,
33 I/O signals.

Tested with 14 factory acceptance test cases and 26 ladder logic tests — all passing.
The safety block also compiles and runs in OpenPLC as Structured Text.

`IEC 61131-3` `Structured Text` `Ladder` `Modbus TCP` `OpenPLC` `ISA-5.1` `ISA-18.2`

### [plc-st-bug-detector-ml](https://github.com/karishmapremnath4/plc-st-bug-detector-ml)
**Finding and fixing logic bugs in PLC Structured Text with machine learning.**

300 generated ST programs containing 8 classes of functional defect — dropped
interlocks, wrong setpoints, missing edge detection — the kind that compile fine and
fail on the plant. Feature extraction, then a decision tree to classify the defect,
then a rule-based repair.

Accuracy went from 81.7% to 100% on 60 held-out programs by fixing the features
rather than the model. The README is honest about why 100% is easier than real code.

`Python` `scikit-learn` `Structured Text`

### [publications](https://github.com/karishmapremnath4/publications)
**Peer-reviewed work, with abstracts and results.**

---

## Publication

**Model predictive controller design using machine learning models and implementation
of parameter tuning**
Giri P., Deepana S., **Karishma P.**, Deepika G. P., Venkatesh S., R. Amirtharajan
*2026 International Conference on Artificial Intelligence and Data Engineering (AIDE)*,
Nitte, India, pp. 326–333
[10.1109/AIDE69088.2026.11545113](https://doi.org/10.1109/AIDE69088.2026.11545113)

An MPC for a laboratory benchtop temperature control station — real closed-loop
control on hardware. Four conventional modelling methods (transfer function, ARX,
Box-Jenkins, state space) compared against four machine learning models (FNN,
decision tree, KNN, ridge regression).

Ridge regression won on every error metric — **MSE 0.0058 and ITAE 12.2788**, a 69%
lower MSE than the feedforward network — and is cheaper to compute, which matters for
real-time control. The paper also sweeps Δu_max, R and Q independently to show where
each parameter stops helping.

---

## Experience

**Apollo Hospital** — Biomedical Engineering Intern · Trichy, India · Jun–Jul 2025
Maintained 25+ diagnostic instruments across patient care units. Diagnosed and
resolved 6 instruments with a senior engineer through hardware-software interfacing,
sensor connectivity and signal validation. Traced recurring connectivity faults and
inconsistent signal thresholds on 3 devices and restored all 3 to service.

**Dalmia Cements** — Process Control & Automation Intern · Dalmiapuram, India · Jul 2024
At a cement unit running crushing, pyroprocessing and packing, monitored 10 process
parameters through PLC and SCADA/HMI dashboards. Traced 10 field instruments across
3 production stages, recording signal type and measurement range for each. Documented
15 process variations with sensor connectivity data.

**CodeBind Technologies** — Embedded Systems Intern · Chennai, India · Jun 2023
Built an automated car parking system with Arduino, IR sensors and embedded C, plus
an Android app. Cut slot-tracking time from 3 minutes to 10 seconds, with correct
availability logged on 20 of 23 test runs.

---

## Skills

**Control & automation** — PLC programming (IEC 61131-3 Ladder and Structured Text),
PID and loop tuning, cascade and ratio control, model predictive control, SCADA and
HMI, Modbus TCP

**Instrumentation & standards** — transducers, instrument index and I/O list, sensor
selection and ranging, 4–20 mA loop design, signal conditioning and calibration, data
acquisition, system identification, ISA-5.1 (P&ID), ISA-18.2 (alarm management),
troubleshooting and commissioning, Factory Acceptance Test

**Programming & tools** — Python, C, Embedded C, Structured Text, SQL, CODESYS,
OpenPLC, MATLAB, Simulink, LabVIEW, AutoCAD, Arduino IDE, Multisim

---

## Education

**Northeastern University**, Boston — MS Electrical & Computer Engineering
Jan 2026 – May 2028 · GPA 3.834 / 4.00 · Coursework: Machine Learning, Robotics

**SASTRA Deemed University**, Thanjavur, India — BTech Electronics & Instrumentation
Engineering · Oct 2021 – Sept 2025
