karishmapremnath4@github: ~$ whoami

█  █  ██  ███  ███  ███ █  █ █   █  ██
█ █  █  █ █  █  █  █    █  █ ██ ██ █  █
██   ████ ███   █   ██  ████ █ █ █ ████
█ █  █  █ █ █   █     █ █  █ █   █ █  █
█  █ █  █ █  █ ███ ███  █  █ █   █ █  █

███  ███  ████ █   █ █  █  ██  ███ █  █
█  █ █  █ █    ██ ██ ██ █ █  █  █  █  █
███  ███  ███  █ █ █ █ ██ ████  █  ████
█    █ █  █    █   █ █  █ █  █  █  █  █
█    █  █ ████ █   █ █  █ █  █  █  █  █

control systems · plc · automation · instrumentation · embedded · ml

**M.S. Electrical & Computer Engineering @ Northeastern** · Boston, MA
Control systems · PLC & automation · instrumentation · embedded · applied ML

[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/karishma-premnath)
[![IEEE Xplore](https://img.shields.io/badge/-IEEE_Xplore-00629B?style=flat-square&logo=ieee&logoColor=white)](https://ieeexplore.ieee.org/document/11545113)
[![Email](https://img.shields.io/badge/-Email-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:premnath.ka@northeastern.edu)
![Location](https://img.shields.io/badge/Boston,_MA-37474f?style=flat-square)
![Open to co-op](https://img.shields.io/badge/Spring_2027_Co--op-1D9E75?style=flat-square)

</div>

---

## 👋 About

I build control systems and then test them until they break.

My background is **Electronics & Instrumentation** — the field side of automation: transducers,
4-20 mA loops, sensor ranging, calibration. I'm now doing an **M.S. in ECE at Northeastern**
(GPA 3.834), working across PLC programming, process control and machine learning.

The through-line in my work is that a control system isn't finished when it compiles. It's
finished when someone has tried to make it fail and written down what happened — which is why
most of the projects below end in a test count, not a demo.

- 📄 **IEEE-published** — MPC paper, AIDE 2026, in IEEE Xplore
- 🏭 **On-site plant experience** — live PLC/SCADA at a cement production unit
- 🧪 **Standards-based work** — IEC 61131-3, ISA-5.1 (P&ID), ISA-18.2 (alarms), FAT
- 🎯 **Seeking a Spring 2027 co-op** in control systems, automation or robotics

---

## 📄 Publication

**Model Predictive Controller Design using Machine Learning Models & Implementation of Parameter Tuning**
*IEEE AIDE 2026 — Technically Co-Sponsored Conference, NMAM Institute of Technology, Nitte, India*
🔗 [ieeexplore.ieee.org/document/11545113](https://ieeexplore.ieee.org/document/11545113)

Implemented and validated a model predictive controller on a **laboratory temperature control
station** — real closed-loop control on hardware. Evaluated **4 machine learning models** (KNN,
feedforward neural network, ridge regression, decision tree) against **4 conventional
identification methods** (state-space, transfer function, ARX, Box-Jenkins) across varying tuning
parameters.

Ridge-based MPC achieved the **lowest MSE (0.0058) and ITAE (12.2788)** among the evaluated
models — beating the neural network on every error metric, at lower computational cost.

---

## 🛠 Projects

### 🏭 Water Treatment Skid — PLC Control System Design & Testing · `Aug 2026`

Built and tested a complete PLC control system for **two-stage water treatment**. Specified
**4 PID loops** (cascade level–flow and ratio control), **12 alarms**, **8 interlocks** and
**33 I/O signals** (7 AI, 4 AO, 14 DI, 8 DO).

Developed **IEC 61131-3 ladder logic and Structured Text**, a **Modbus TCP** plant simulation and
a process HMI. Executed **14 FAT cases and 26 logic tests** — found **6 design defects across the
40 test cases** and rectified all 6 for a **100% pass**.

![IEC61131](https://img.shields.io/badge/IEC_61131--3-0B5394?style=flat-square)
![CODESYS](https://img.shields.io/badge/CODESYS-1D9E75?style=flat-square)
![OpenPLC](https://img.shields.io/badge/OpenPLC-E8710A?style=flat-square)
![Modbus](https://img.shields.io/badge/Modbus_TCP-455A64?style=flat-square)
![ISA](https://img.shields.io/badge/ISA--5.1-6A1B9A?style=flat-square)

---

### 🐛 ML-Assisted PLC Structured Text Bug Detection & Rule-Based Repair · `Jun 2026`

Developed a dataset of **300 PLC Structured Text programs** featuring **8 functional defect
classes** — disabled interlock, incorrect setpoint and similar — the bugs that **compile
successfully but cause failures during operation**.

Implemented a Python workflow for automated feature extraction from code, then trained a decision
tree to predict the functional error. Raised defect classification accuracy from an **81.7%
baseline to 100%** over **60 held-out programs**, and rectified all 60 single-defect test programs.

![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![Structured Text](https://img.shields.io/badge/Structured_Text-0B5394?style=flat-square)

---

### 🌡 Predictive Controller Design & Tuning Strategies for a Temperature Process · `May 2025`

Designed and evaluated a model predictive controller incorporating **4 ML methods** — KNN, FNN,
ridge regression and decision tree — under varying tuning parameters. Ridge-based MPC delivered
the best control performance and became the basis for the **IEEE publication** above.

![MATLAB](https://img.shields.io/badge/MATLAB-0076A8?style=flat-square&logo=mathworks&logoColor=white)
![Simulink](https://img.shields.io/badge/Simulink-FF7A00?style=flat-square)
![Python](https://img.shields.io/badge/Python-3670A0?style=flat-square&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)

---

### 🤖 RPA UiPath — Capstone Project · `Aug 2024`

Repetitive data generation, email notification and form submission tasks required extensive manual
effort. Built an automation solution in **UiPath**, using UiPath Orchestrator to schedule and
manage the workflows for error-free process automation.

![UiPath](https://img.shields.io/badge/UiPath-FA4616?style=flat-square&logo=uipath&logoColor=white)
![RPA](https://img.shields.io/badge/RPA-37474f?style=flat-square)

---

### ❤️ Smart Wearable Respiratory & Heart Rate Monitor · `May 2024`

Conventional monitoring needs separate transducers per vital sign. Built a wearable belt that
monitors **both respiratory rate and heart rate from a single force-sensitive resistor**.

Implemented and calibrated the analog signal chain: **I-V amplification** across a 16-point load
curve from **0.98 to 19 N**, an **LM324 active low-pass filter (0.45 Hz)** for respiration, and a
**band-pass filter (2.5–5 Hz)** for the ballistocardiogram. Validated across **48–108 BPM** and
**8–23 breaths/min**.

![Embedded C](https://img.shields.io/badge/Embedded_C-00599C?style=flat-square&logo=c&logoColor=white)
![LM324](https://img.shields.io/badge/LM324-455A64?style=flat-square)
![Signal Processing](https://img.shields.io/badge/Signal_Processing-37474f?style=flat-square)

---

### 🅿️ Automated Smart Parking System · `Jun 2023`

Manual tracking of **6 parking slots** took 3 minutes per scan and delayed vehicle entry. Designed
and deployed an automated system using **Arduino, IR sensors and embedded C**, integrating sensor
hardware with control software and an **Android app** for live slot status. Cut tracking time to
**10 seconds — an 18× reduction** — with correct availability logged on **20 of 23 test runs**.

![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat-square&logo=arduino&logoColor=white)
![Embedded C](https://img.shields.io/badge/Embedded_C-00599C?style=flat-square&logo=c&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?style=flat-square&logo=android&logoColor=white)

---

## 💼 Experience

**Apollo Hospital** — *Biomedical Engineering Intern* · Trichy, India · `Jun 2025 – Jul 2025`
Maintained and serviced **25+ diagnostic instruments** across patient care units. Assisted a senior
engineer in diagnosing and resolving **6 medical instruments** through hardware-software
interfacing, sensor connectivity and signal validation. Identified recurring hardware connectivity
issues and inconsistent signal thresholds on **3 devices**, restoring all 3 to operation.

**Dalmia Cements** — *Process Control & Automation Intern* · Dalmiapuram, India · `Jul 2024`
At a cement production unit running crushing, pyroprocessing and packing, monitored **10 process
parameters** through **PLC and SCADA/HMI dashboards**. Traced **10 field instruments across 3
production stages**, recording signal type and measurement range for each. Documented **15 process
variations** with sensor connectivity data, with no wiring faults found.

**CodeBind Technologies** — *Embedded Systems Intern* · Chennai, India · `Jun 2023`
Designed and deployed the automated car parking system described above — Arduino, IR sensors and
embedded C with an Android app — reducing scan time from 3 minutes to 10 seconds.

---

## 🧰 Tech Stack

**Control & Automation**
![PLC](https://img.shields.io/badge/IEC_61131--3-0B5394?style=for-the-badge)
![CODESYS](https://img.shields.io/badge/CODESYS-1D9E75?style=for-the-badge)
![OpenPLC](https://img.shields.io/badge/OpenPLC-E8710A?style=for-the-badge)
![SCADA](https://img.shields.io/badge/SCADA_/_HMI-455A64?style=for-the-badge)
![Modbus](https://img.shields.io/badge/Modbus_TCP-37474f?style=for-the-badge)

**Languages**
![Python](https://img.shields.io/badge/Python-3670A0?style=for-the-badge&logo=python&logoColor=white)
![C](https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white)
![Structured Text](https://img.shields.io/badge/Structured_Text-0B5394?style=for-the-badge)
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

**Tools & Software**
![MATLAB](https://img.shields.io/badge/MATLAB-0076A8?style=for-the-badge&logo=mathworks&logoColor=white)
![Simulink](https://img.shields.io/badge/Simulink-FF7A00?style=for-the-badge)
![LabVIEW](https://img.shields.io/badge/LabVIEW-FFDB00?style=for-the-badge&logo=labview&logoColor=black)
![AutoCAD](https://img.shields.io/badge/AutoCAD-C0392B?style=for-the-badge&logo=autodesk&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino_IDE-00979D?style=for-the-badge&logo=arduino&logoColor=white)
![Multisim](https://img.shields.io/badge/Multisim-1565c0?style=for-the-badge)
![UiPath](https://img.shields.io/badge/UiPath-FA4616?style=for-the-badge&logo=uipath&logoColor=white)

```python
skills = {
  "control"          : ["PID + loop tuning", "Cascade control", "Ratio control",
                        "Model Predictive Control", "System identification"],
  "plc_automation"   : ["IEC 61131-3 Ladder", "Structured Text", "CODESYS", "OpenPLC",
                        "SCADA / HMI", "Modbus TCP"],
  "instrumentation"  : ["Transducers", "Instrument index + I/O list",
                        "Sensor selection & ranging", "4-20 mA loop design",
                        "Signal conditioning", "Calibration", "Data acquisition",
                        "ISA-5.1 (P&ID)", "ISA-18.2 (alarms)",
                        "Troubleshooting & commissioning", "Factory Acceptance Test"],
  "embedded"         : ["Embedded C", "Arduino", "Analog front ends",
                        "Active filter design", "Sensor interfacing"],
  "ml_data"          : ["Ridge regression", "Decision trees", "KNN", "Feedforward NN",
                        "Predictive modeling", "Pattern recognition", "scikit-learn"],
}
```

---

## 🎓 Education

**Northeastern University** — Boston, MA · `Jan 2026 – Expected May 2028`
M.S. Electrical & Computer Engineering · **GPA 3.834 / 4.00**
Relevant coursework: Machine Learning, Robotics

**SASTRA Deemed University** — Thanjavur, India · `Oct 2021 – Sept 2025`
B.Tech, Electronics & Instrumentation Engineering

---

## 📊 GitHub Stats

<p align="center">
  <img src="https://www.gitskins.com/api/section/stats?username=karishmapremnath4&theme=github-dark" alt="GitHub Stats" />
</p>

---

## 🤝 Connect With Me

<p align="center">
  <img src="https://www.gitskins.com/api/section/social?username=karishmapremnath4&theme=github-dark" alt="karishmapremnath4 social links" />
</p>

<div align="center">

[![LinkedIn](https://img.shields.io/badge/Connect%20on%20LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/karishma-premnath)
[![IEEE](https://img.shields.io/badge/Read%20the%20IEEE%20paper-00629B?style=for-the-badge&logo=ieee&logoColor=white)](https://ieeexplore.ieee.org/document/11545113)
[![Email](https://img.shields.io/badge/Email%20me-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:premnath.ka@northeastern.edu)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/karishmapremnath4)

**Open to Spring 2027 co-op** — control systems · PLC & automation · robotics · embedded · applied ML
Available January 2027 · Boston, MA

</div>
