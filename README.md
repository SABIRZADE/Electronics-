-------------------
1.Topic

https://www.slideshare.net/slideshow/comprehensive-technical-report-on-field-effect-transistors-fets-and-their-applications/287120657

verified by: physics teacher azerbaijan telman askeraliyev (fizika muellimi) – contact: https://www.linkedin.com/in/physics-teacher-azerbaijan-telman-askeraliyev/
https://www.instagram.com/physics_teacher_azerbaijan

# Field Effect Transistors (FETs) — Arduino-Based Switching Circuit

A 7-page comprehensive technical report covering FET theory, circuit design,
MOSFET characteristics, Arduino control code, and practical switching
applications using a dual 9V battery configuration.

**Authors:** Nihat Sabirzade · Murad Ibrahimov · Ilkin Mecidov
**Verified by:** Telman Askeraliyev — Physics Teacher, Azerbaijan, Baku (Fizika Muellimi)
**Date:** April 2026

---

## Report Overview

| # | Section | Content |
|---|---------|---------|
| 01 | Introduction to FETs | FET vs BJT comparison, FET families — JFET, Enhancement & Depletion MOSFET |
| 02 | Circuit Overview & Diagram | Arduino UNO + dual 9V battery switching circuit, component roles |
| 03 | Working Principle | Step-by-step gate control operation, voltage & current summary |
| 04 | MOSFET Characteristics | N-Channel parameters, operating regions, Arduino compatibility |
| 05 | Arduino Control Code | Gate control sketch, PWM analog control, safety design notes |
| 06 | Summary & Conclusion | 7 key takeaways, real-world application table |

---

## Circuit Specifications

| Parameter | Value |
|-----------|-------|
| Microcontroller | Arduino UNO |
| Power Supply | 2× 9V batteries (18V series total) |
| Arduino I/O HIGH | 5V |
| Gate Threshold V_th | ~2–4V (typical N-Channel MOSFET) |
| Gate Resistor R_g | ~1 kΩ |
| Pull-Down Resistor R_pd | ~10 kΩ |
| Recommended MOSFET | IRLZ44N (logic-level) / IRF540N |

---

## FET vs BJT Comparison

| Property | FET | BJT |
|----------|-----|-----|
| Input Impedance | MΩ → TΩ | kΩ |
| Control Type | Voltage-controlled | Current-controlled |
| Noise Figure | Very Low | Moderate |
| Thermal Stability | High | Lower |

---

## Arduino Sketch

```cpp
const int FET_GATE_PIN = 9;   // PWM-capable pin

void setup() {
  pinMode(FET_GATE_PIN, OUTPUT);
  digitalWrite(FET_GATE_PIN, LOW);  // Start with FET OFF
}

void loop() {
  digitalWrite(FET_GATE_PIN, HIGH); // FET ON
  delay(1000);
  digitalWrite(FET_GATE_PIN, LOW);  // FET OFF
  delay(1000);
}
```

PWM control via `analogWrite()` enables motor speed control and LED dimming.

---

## Applications Covered

| Application | FET Role | Load Example |
|-------------|----------|-------------|
| DC Motor Speed Control | PWM switch | 12V DC motor |
| LED Strip Dimming | PWM switch | 12V LED strip |
| Relay Driver | Logic switch | High-voltage relay coil |
| Battery Charger | Regulating switch | Li-ion charging circuit |
| Solenoid Valve Control | On/off switch | Pneumatic valve |

---

## Key Safety Notes

- **Gate Resistor** — Always use 100Ω–1kΩ to prevent ringing oscillations
- **Pull-Down Resistor** — 10kΩ between gate and source ensures FET is OFF when Arduino resets
- **Flyback Diode** — Required for inductive loads (motors, relays) to suppress voltage spikes
- **Common Ground** — Arduino GND, FET source, and battery negative must be shared

---

## Files

| File | Description |
|------|-------------|
| `FET_report.pdf` | Full 7-page technical report with diagrams |
| `fet_gate_control.ino` | Arduino sketch for FET gate switching |

---

## Subject

- **Field:** Electronics / Microcontroller Interfacing
- **Type:** Comprehensive Technical Report
- **Language:** English
- **Location:** Azerbaijan, Baku
---------------------
2.Topic
https://www.slideshare.net/slideshow/comprehensive-technical-report-on-voltage-divider-circuits-and-applications/287239518

verified by: physics teacher azerbaijan telman askeraliyev (fizika muellimi) – contact: https://www.linkedin.com/in/physics-teacher-azerbaijan-telman-askeraliyev/
https://www.instagram.com/physics_teacher_azerbaijan

# Voltage Divider — Comprehensive Technical Report

A 7-page comprehensive technical report covering the theory, mathematical
derivation, loading effects, practical applications, and design guidelines
of the voltage divider circuit.

**Authors:** Nihat Sabirzade · Murad Ibrahimov · Ilkin Mecidov
**Verified by:** Telman Askeraliyev — Physics Teacher, Azerbaijan, Baku
**Date:** April 2026

---

## Report Overview

| # | Section | Content |
|---|---------|---------|
| 01 | What is a Voltage Divider? | Definition, key properties, common applications |
| 02 | Circuit Diagram & Components | Schematic, component roles, circuit behaviour, KVL |
| 03 | Mathematical Derivation | Series current, voltage formulas, KVL verification, numerical example |
| 04 | Divider Ratio & Loaded Divider | Ratio table, loading effect, R_L rule of thumb |
| 05 | Practical Applications | Level shifting, ADC scaling, transistor biasing, potentiometer |
| 06 | Summary & Conclusion | All key formulas, 7 key takeaways |

---

## Key Formulas

| Quantity | Formula |
|----------|---------|
| Series current | `I = VS / (R1 + R2)` |
| Upper voltage | `V1 = VS × R1 / (R1 + R2)` |
| Output voltage | `V2 = VS × R2 / (R1 + R2)` |
| Divider ratio | `k = R2 / (R1 + R2)` |
| KVL check | `V1 + V2 = VS` |
| Loaded output | `R2_eff = R2 × RL / (R2 + RL)` |

---

## Numerical Example

| Parameter | Value |
|-----------|-------|
| Supply voltage VS | 12 V |
| R1 | 3 kΩ |
| R2 | 1 kΩ |
| Current I | 3 mA |
| V1 | 9 V (75%) |
| V2 (output) | 3 V (25%) |
| Divider ratio k | 0.25 |

---

## Practical Applications Covered

- **Logic Level Shifting** — 5V to 3.3V for ESP32 / STM32 interfaces
- **ADC Sensor Scaling** — 0–12V sensor down to 0–5V Arduino input
- **Transistor Base Biasing** — Setting BJT Q-point via VCC divider
- **Potentiometer** — Variable divider for volume controls and trimmers

---

## Key Takeaways

- Output ratio k depends only on R1 and R2, not on supply voltage
- Loading effect: connecting R_L across R2 reduces V2 — keep R1+R2 << R_L
- Use 1% tolerance (E96 series) resistors for accurate ratios
- The voltage divider appears in virtually every electronics circuit

---

## Files

| File | Description |
|------|-------------|
| `voltage_divider_report.pdf` | Full 7-page technical report with diagrams |

---

## Subject

- **Field:** Electronics / Circuit Theory
- **Type:** Comprehensive Technical Report
- **Language:** English
- **Location:** Azerbaijan, Baku

------------------------
3.Topic

verified by: physics teacher azerbaijan telman askeraliyev (fizika muellimi) – contact: https://www.linkedin.com/in/physics-teacher-azerbaijan-telman-askeraliyev/
https://www.instagram.com/physics_teacher_azerbaijan

https://www.academia.edu/166064683/Technical_Laboratory_Report_Automatic_Light_Sensing_and_Voltage_Divider_Circuit_Nihat_Sabirzade_Murad_Ibrahimov_Ilkin_Mecidov_Baris_Huseynov_Verified_by_Physics_Teacher_Azerbaijan_Telman_Askeraliyev_Fizika_Muellimi_Azerbaijan_Baku_

# Automatic Light Sensing & Voltage Divider Circuit — Technical Lab Report

A full technical laboratory report documenting the design, simulation,
analysis, and troubleshooting of an LDR-triggered passive speaker circuit
powered by a 9V battery.

**Authors:** Nihat Sabirzade · Murad Ibrahimov · Ilkin Mecidov · Baris Huseynov
**Verified by:** Telman Askeraliyev — Physics Teacher, Azerbaijan, Baku
**Date:** 28 April 2026

---

## Report Overview

| # | Section | Content |
|---|---------|---------|
| 1 | Circuit Description | Component list, circuit purpose, LDR voltage divider principle |
| 2 | Schematic Analysis | Power stage, sensing stage, output stage — node voltage table |
| 3 | Predictive Calculations | Voltage divider formula, current draw, power dissipation |
| 4 | Simulation Results | VP1 anomaly analysis, expected vs measured behaviour |
| 5 | Troubleshooting Guide | 7 common faults with causes and recommended fixes |
| 6 | Review Questions | Simulation artefact explanation + dark-activated alarm modification |

---

## Circuit Specifications

| Parameter | Value |
|-----------|-------|
| Supply Voltage | 9V DC (BAT1) |
| Fixed Resistor R1 | 10 kΩ |
| LDR Model | ORCH_LDR |
| Simulation Tool | Proteus / EasyEDA |
| Measured VP1 | 12.47 V (anomalous — analysed in report) |
| Divider Current | 0.45 mA (balanced condition) |
| Power in R1 | ≈ 2.025 mW |

---

## Key Findings

- LDR and R1 form a voltage divider — output voltage varies with ambient light
- VP1 reading of 12.47V exceeds supply due to floating probe (simulation artefact)
- Divider current (0.45 mA) is too low to directly drive a passive speaker
- A BJT driver stage (BC547 / 2N2222) is required for proper speaker activation
- Potentiometer replacement of R1 allows adjustable light sensitivity

---

## Recommended Circuit Improvements

- **NPN Transistor** (BC547) — current amplification to drive the speaker
- **Base Resistor** (1 kΩ) — limits base current to protect transistor
- **Potentiometer** (10 kΩ) — replaces R1 for adjustable sensitivity
- **Flyback Diode** (1N4007) — protects transistor from inductive spikes
- **Decoupling Capacitor** (100 µF) — filters supply noise

---

## Files

| File | Description |
|------|-------------|
| `lab_report.pdf` | Full technical report with circuit diagram |
| `circuit_schematic/` | Simulation files (Proteus / EasyEDA) |

---

## Subject

- **Field:** Electronics / Circuit Theory
- **Type:** Technical Laboratory Report
- **Language:** English
- **Location:** Azerbaijan, Baku
-------------------
4.Topic

verified by: physics teacher azerbaijan telman askeraliyev (fizika muellimi) – contact: https://www.linkedin.com/in/physics-teacher-azerbaijan-telman-askeraliyev/
https://www.instagram.com/physics_teacher_azerbaijan

https://www.slideshare.net/slideshow/network-security-market-opportunities-and-paint-points/287350402

# Network Security — Market Opportunities & Pain Points

A data-driven 9-slide presentation analyzing the global network security
market, key growth opportunities, critical industry pain points, and
strategic recommendations.

**Authors:** Nihat Sabirzade · Emil Zulfuqarov
**Verified by:** Telman Askeraliyev — Physics Teacher, Azerbaijan, Baku (Fizika Muellimi)

---

## Slides Overview

| # | Slide | Key Content |
|---|-------|-------------|
| 01 | Title | Market snapshot — $298B, 3,500+ daily attacks, $4.9M avg breach cost |
| 02 | Agenda | 6-section roadmap of the presentation |
| 03 | Market Overview & Size | 12.3% CAGR, growth chart 2020–2028, #1 fastest growing IT sector |
| 04 | Key Market Opportunities | Cloud Security $68B, Zero Trust $52B, AI Security $38B, OT/ICS $22B |
| 05 | Critical Pain Points | Skill gap, alert fatigue, patch delays, visibility gaps, budget, compliance |
| 06 | Threat Landscape | Ransomware, phishing, supply chain, nation-state — 2024 threat distribution chart |
| 07 | Competitive Landscape | Market share: Palo Alto, Fortinet, CrowdStrike, Cisco, Check Point |
| 08 | Recommendations | Zero Trust, SOAR automation, skills gap solutions, platform consolidation |
| 09 | Key Takeaways | Summary of core findings and call to action |

---

## Key Statistics

- **$298B** — Projected global cybersecurity market by 2028
- **12.3%** — CAGR 2023–2028
- **3,500+** — Daily cyberattacks worldwide
- **$4.9M** — Average cost of a data breach
- **277 days** — Average time to detect a breach
- **3.5M** — Unfilled cybersecurity jobs globally

---

## Tools Used

- Presentation design & data visualization
- Charts: Market growth, threat distribution, competitive market share

---

## Subject

- **Field:** Network Security / Cybersecurity
- **Type:** Market Research & Analysis
- **Language:** English
- **Location:** Azerbaijan, Baku
--------------------
5.Topic
verified by: physics teacher azerbaijan telman askeraliyev (fizika muellimi) – contact: https://www.linkedin.com/in/physics-teacher-azerbaijan-telman-askeraliyev/
https://www.instagram.com/physics_teacher_azerbaijan

https://www.slideshare.net/slideshow/comprehensive-introduction-to-operational-amplifiers-principles-and-applications/287466328
# The Operational Amplifier — Educational Presentation

An 8-slide presentation covering the fundamentals of operational amplifiers (Op-Amps),
created as part of an Electronics & Circuit Theory course.

**Authors:** Nihat Sabirzade • Murad Ibrahimov
**Verified by:** Telman Askeraliyev — Physics Teacher, Azerbaijan, Baku (Fizika Muellimi)

---

## Topics Covered

1. **Introduction to Op-Amps** — Symbol, terminals, supply rails, open-loop gain
2. **Input Modes & Parameters** — Differential mode, common mode, CMRR, slew rate
3. **Negative Feedback** — Effects on gain, bandwidth, impedance, and distortion
4. **Impedances, Bias Current & Offset Voltage** — Input/output impedance, Vos, Ib
5. **Frequency Response** — Open-loop vs closed-loop, Bode plot, gain-bandwidth product
6. **Comparators & Summing Amplifiers** — Schmitt trigger, virtual ground, weighted sum
7. **Integrators & Differentiators** — RC-based op-amp circuits, waveform conversion
8. **Summary** — Key concepts recap

---

## Files

| File | Description |
|------|-------------|
| `opamp_presentation.pdf` | Final presentation in PDF format |
| `opamp_presentation.pptx` | Editable PowerPoint source file |
| `opamp_presentation.js` | Source script used to generate the slides (PptxGenJS) |
| `opamp.png` | Op-amp circuit diagram used in the presentation |

---

## Tools Used

- **PptxGenJS** — Programmatic slide generation
- **LibreOffice** — PPTX to PDF conversion
- **Node.js** — Runtime environment

---

## Course Info

- **Subject:** Electronics & Circuit Theory
- **Topic:** The Operational Amplifier
- **Location:** Azerbaijan, Baku
