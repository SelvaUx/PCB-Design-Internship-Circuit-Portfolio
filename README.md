<p align="center">
  <img src="https://img.shields.io/badge/KiCad-10.0-314CB0?style=for-the-badge&logo=kicad&logoColor=white" alt="KiCad 10.0"/>
  <img src="https://img.shields.io/badge/Projects-10-00C853?style=for-the-badge" alt="10 Projects"/>
  <img src="https://img.shields.io/badge/PCB_Design-Internship-FF6D00?style=for-the-badge" alt="PCB Design Internship"/>
  <img src="https://img.shields.io/badge/License-MIT-blue?style=for-the-badge" alt="MIT License"/>
</p>

<h1 align="center">⚡ PCB Design Internship — Circuit Portfolio</h1>

<p align="center">
  <strong>A collection of 10 production-ready schematic & PCB layout designs</strong><br/>
  <em>From fundamental analog circuits to motor control systems — all designed in KiCad</em>
</p>

---

## 👤 About the Author

**Selva Pandi** — *Selva.Ux* online

> An ECE student who decided that waiting to be qualified was a worse plan than just building the thing.

I build for the messy, low-bandwidth, real world — where people need technology that actually functions. My engineering philosophy is simple: **offline first, privacy always, real hardware required**. I don't trust solutions that work only in ideal conditions.

From custom AI assistants to fiber fault detection engines, from IoT aquaculture platforms to portfolio sites with mini-labs inside — the list doesn't stop because the curiosity doesn't stop.

| | |
|---|---|
| 🌐 **Portfolio + Lab** | [selvaux.in](https://selvaux.in) |
| 📫 **Email** | [selva.ux@yahoo.com](mailto:selva.ux@yahoo.com) |
| 💡 **Specialization** | Offline AI · Edge Computing · Embedded Systems · Custom OS |

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| [**KiCad EDA**](https://www.kicad.org/) (v10.0) | Primary CAD suite |
| **Eeschema** | Schematic capture, including hierarchical multi-sheet designs |
| **Pcbnew** | PCB routing, footprint assignment, copper zone fills & board layout |
| **SPICE** | Integrated simulation models for circuit verification |

---

## 📂 Repository Structure

```
📦 Iternship PCB/
├── 🌉 Bridge Rectifier/          → Full-wave AC-to-DC rectifier
├── 🚨 Buzzer Alarm/              → Transistor-driven buzzer with push-button
├── 💡 LED Blink Using IC555/     → Astable multivibrator LED flasher
├── 🔌 LED Circuit/               → Multi-LED driver with transistor switching
├── 📉 Low Pass Filter/           → Passive RC low-pass filter
├── 🎵 METRONOME/                 → 555 Timer metronome with speaker output
├── ⚙️ Motor Speed Controller/    → PWM DC motor speed control via L293 H-Bridge
├── 💡 Simple LED Circuit/        → Hierarchical push-button LED (multi-sheet)
├── ⚡ Voltage Divider/           → Two-resistor voltage divider
├── 🔌 Voltage Regulator/         → +5V linear supply (hierarchical design)
├── 🔌 Voltage Regulator - Copy/  → Same circuit, flat single-sheet layout
└── 📄 README.md
```

Each project folder contains:
```text
├── [Project].kicad_pro     # KiCad Project File
├── [Project].kicad_sch     # Main Schematic (or Parent Sheet)
├── [Project].kicad_pcb     # PCB Layout File
├── [Project].kicad_prl     # Project Local Settings
├── [Sub-sheets].kicad_sch  # Sub-schematics (hierarchical designs only)
└── .history/               # KiCad automatic local history backups
```

---

## 📋 Projects Catalog

### 1. 🌉 Bridge Rectifier

| | |
|---|---|
| **Category** | Power Electronics — AC/DC Conversion |
| **Schematic** | `Bridge Rectifier/Bridge Rectifier.kicad_sch` |
| **PCB** | `Bridge Rectifier/Bridge Rectifier.kicad_pcb` |

**Circuit Goal:** Converts a dual AC voltage source into a smoothed, single-polarity DC output.

**Bill of Materials:**

| Ref | Component | Value | Purpose |
|-----|-----------|-------|---------|
| D1–D4 | `1N4007` Rectifier Diode | — | Bridge configuration |
| C1 | Polarized Electrolytic Capacitor | `4000µF` | Ripple smoothing reservoir |
| R1 | Resistor | `1kΩ` | Load / bleeder resistor |
| V1, V2 | Sinusoidal AC Source | `12V` | Simulation sources |

**How It Works:** The four diodes form a bridge that rectifies both halves of the AC waveform. The large `4000µF` capacitor acts as a low-pass reservoir to minimize voltage ripple, delivering a stable DC output across `R1`.

---

### 2. 🚨 Buzzer Alarm

| | |
|---|---|
| **Category** | Digital Logic — Transistor Switching |
| **Schematic** | `Buzzer Alarm/Buzzer Alarm.kicad_sch` |
| **PCB** | `Buzzer Alarm/Buzzer Alarm.kicad_pcb` |

**Circuit Goal:** A transistor-driven active buzzer alarm actuated by a manual push-button switch.

**Bill of Materials:**

| Ref | Component | Value | Purpose |
|-----|-----------|-------|---------|
| BZ1 | Active Buzzer | — | Sound output |
| Q1 | `BC547` NPN BJT | — | Low-side electronic switch |
| SW1 | Push Button (SPST) | — | Manual trigger |
| R1 | Resistor | `10kΩ` | Base current-limiting |
| R2 | Resistor | `1kΩ` | Bias resistor |

**How It Works:** The `BC547` transistor acts as a low-side switch. Pressing `SW1` drives base current into `Q1` via `R1`, saturating the transistor and allowing current to flow through the buzzer to ground.

---

### 3. ⏱️ LED Blink Using IC555

| | |
|---|---|
| **Category** | Timing & Oscillation — Astable Multivibrator |
| **Schematic** | `LED Blink Using IC555/LED Blink Using IC555.kicad_sch` |
| **PCB** | `LED Blink Using IC555/LED Blink Using IC555.kicad_pcb` |

**Circuit Goal:** A classic 555 Timer astable oscillator that pulses an LED indicator at a defined frequency.

**Bill of Materials:**

| Ref | Component | Value | Purpose |
|-----|-----------|-------|---------|
| U1 | `NA555P` Timer IC | — | Oscillator core |
| R1 | Timing Resistor | `1MΩ` | Controls charge time T_high |
| R2 | Timing Resistor | `1MΩ` | Controls charge & discharge T_low |
| C1 | Timing Capacitor | `1.5nF` | RC timing element |
| C2 | Bypass Capacitor | `0.01µF` | Control voltage pin decoupling |
| D1 | Red LED | — | Pulse indicator |
| R3 | Resistor | `470Ω` | LED current-limiting |
| J1 | 2-pin Screw Terminal | — | Power input connector |

**How It Works:** The 555 continuously charges and discharges `C1` between ⅓ and ⅔ of VCC through `R1` and `R2`. This produces a continuous square wave on pin 3 (Output), causing LED `D1` to flash at a rate defined by:

$$f = \frac{1.44}{(R1 + 2 \cdot R2) \cdot C1}$$

---

### 4. 🔌 LED Circuit

| | |
|---|---|
| **Category** | Transistor Switching — Multi-LED Driver |
| **Schematic** | `LED Circuit/LED Circuit.kicad_sch` |
| **PCB** | `LED Circuit/LED Circuit.kicad_pcb` |

**Circuit Goal:** A multi-channel LED driver circuit using `BC547` NPN transistors as electronic switches, each controlling individual LEDs through current-limiting resistors.

**Bill of Materials:**

| Ref | Component | Value | Purpose |
|-----|-----------|-------|---------|
| BT1 | Battery Cell | — | DC power source |
| Q1–Q3 | `BC547` NPN BJT | — | LED driver switches |
| D1–D9 | LEDs | — | Light indicators |
| R1–R3 | Resistor | `470Ω` | LED current-limiting |
| R4–R6 | Resistor | `10kΩ` | Base current-limiting |
| C1–C3 | Capacitor | — | Decoupling / timing |

**How It Works:** Each `BC547` transistor is independently driven via a base resistor. When the transistor is saturated, it provides a ground path for the corresponding LED string. The `470Ω` resistors limit LED forward current, and `10kΩ` resistors control transistor base drive. This design demonstrates parallel transistor switching for multi-LED arrays.

---

### 5. 📉 Low Pass Filter

| | |
|---|---|
| **Category** | Signal Conditioning — Passive Filter |
| **Schematic** | `Low Pass Filter/Low Pass Filter.kicad_sch` |
| **PCB** | `Low Pass Filter/Low Pass Filter.kicad_pcb` |

**Circuit Goal:** A basic passive single-pole RC Low Pass Filter (LPF).

**Bill of Materials:**

| Ref | Component | Value | Purpose |
|-----|-----------|-------|---------|
| R1 | Resistor | `1kΩ` | Filter element |
| C1 | Polarized Capacitor | `1µF` | Filter element |
| J1 | 2-pin Screw Terminal | — | I/O connector |

**How It Works:** Attenuates high-frequency signals while passing lower-frequency components. The cutoff frequency is:

$$f_c = \frac{1}{2\pi \cdot R1 \cdot C1} \approx 159.15 \text{ Hz}$$

Signals above this frequency are progressively attenuated at –20 dB/decade.

---

### 6. 🎵 METRONOME

| | |
|---|---|
| **Category** | Timing & Audio — Audible Click Generator |
| **Schematic** | `METRONOME/METRONOME.kicad_sch` |
| **PCB** | `METRONOME/METRONOME.kicad_pcb` |

**Circuit Goal:** A 555 Timer-based electronic metronome that generates periodic audible clicks through a speaker, with adjustable tempo via a variable resistor (potentiometer).

**Bill of Materials:**

| Ref | Component | Value | Purpose |
|-----|-----------|-------|---------|
| IC555 | 555 Timer IC | — | Astable oscillator core |
| BT1 | Battery Cell | — | DC power source |
| LS1 | Speaker | — | Audio output (CUI CMR-1206S) |
| R1 | Resistor | — | Timing resistor |
| R2 | Variable Resistor | — | Tempo control (potentiometer) |
| R3 | Variable Resistor | — | Fine tuning |
| C1–C3 | Capacitors | — | Timing & decoupling |

**How It Works:** The 555 Timer runs in astable mode, generating a square wave output. The variable resistors `R2` and `R3` allow the user to adjust the oscillation frequency (tempo). The output drives a speaker `LS1` to produce rhythmic audible clicks. The timing capacitor and RC network set the beat interval.

---

### 7. ⚙️ Motor Speed Controller

| | |
|---|---|
| **Category** | Motor Control — PWM Speed Regulation |
| **Schematic** | `Motor Speed Controller/Motor Speed Controller.kicad_sch` |
| **PCB** | `Motor Speed Controller/Motor Speed Controller.kicad_pcb` |

**Circuit Goal:** A PWM-based DC motor speed controller using a 555 Timer IC for pulse generation and an L293 Quadruple Half-H Driver for motor drive, with flyback protection and direction control.

**Bill of Materials:**

| Ref | Component | Value | Purpose |
|-----|-----------|-------|---------|
| U1 | `ICM7555xP` Timer IC | — | PWM pulse generator (astable) |
| U2 | `L293` Motor Driver | — | Quadruple Half-H bridge driver |
| M1 | DC Motor | — | Load |
| D2, D3 | `1N4001` Diode | — | Flyback / freewheeling protection |
| SW1 | Nidec CAS-120A1 Switch | — | Motor on/off control |
| R1 | Resistor | `1kΩ` | Timing / bias |
| R2, R4 | Resistor | `100Ω` | Current limiting |
| R3 | Resistor | — | Timing |
| C1 | Polarized Capacitor | `10µF` | Timing / decoupling |
| J1 | 2-pin Screw Terminal | — | Power input connector |

**How It Works:** The `ICM7555` generates a variable-duty-cycle PWM signal that feeds into the L293 H-Bridge driver's enable and input pins. By varying the duty cycle, the average voltage delivered to the DC motor changes, controlling its speed. The `1N4001` diodes provide flyback protection against voltage spikes from the motor's inductive load. The L293 handles the power switching, isolating the low-power timer circuit from the high-current motor.

---

### 8. 💡 Simple LED Circuit

| | |
|---|---|
| **Category** | Digital Basics — Hierarchical Design |
| **Schematic** | `Simple LED Circuit/Simple LED Circuit.kicad_sch` (Master) |
| **PCB** | `Simple LED Circuit/Simple LED Circuit.kicad_pcb` |

**Circuit Goal:** A modular, push-button-activated LED circuit using a **multi-sheet hierarchical design** in KiCad.

**Schematic Architecture:**

| Sheet | Components | Role |
|-------|------------|------|
| **Master** (`Simple LED Circuit.kicad_sch`) | — | Declares & links sub-sheets |
| **Power** (`power.kicad_sch`) | `BT2`: Battery, `SW2`: Push Button | Power supply & control |
| **LED** (`led.kicad_sch`) | `D2`: LED, `R2`: Current-Limiting Resistor | Load & indicator |

**How It Works:** When the button is held down, current flows from the battery through the resistor and lights the LED. This project demonstrates clean, modular circuit design using KiCad's hierarchical page linking system.

---

### 9. ⚡ Voltage Divider

| | |
|---|---|
| **Category** | Analog Fundamentals — Passive Voltage Scaling |
| **Schematic** | `Voltage Divider/Voltage Divider.kicad_sch` |
| **PCB** | `Voltage Divider/Voltage Divider.kicad_pcb` |

**Circuit Goal:** A fundamental two-resistor voltage divider to step down DC voltage.

**Bill of Materials:**

| Ref | Component | Value | Purpose |
|-----|-----------|-------|---------|
| V1 | DC Voltage Source | `5V` | Input (simulation) |
| R1 | Resistor | `1kΩ` | Upper divider arm |
| R2 | Resistor | `1kΩ` | Lower divider arm |

**How It Works:** Splits the input voltage proportionally to the resistor ratio. With two equal `1kΩ` resistors:

$$V_{out} = V_{in} \cdot \frac{R2}{R1 + R2} = 5\text{V} \cdot \frac{1\text{k}\Omega}{2\text{k}\Omega} = 2.5\text{V}$$

---

### 10. 🔌 Voltage Regulator (+5V Linear Power Supply)

| | |
|---|---|
| **Category** | Power Electronics — Linear Regulated Supply |
| **Schematic** | `Voltage Regulator/Voltage Regulator.kicad_sch` (Master) |
| **PCB** | `Voltage Regulator/Voltage Regulator.kicad_pcb` |

**Circuit Goal:** A complete +5V regulated linear power supply that rectifies AC input, filters noise, and outputs a stable 5V DC rail.

**Schematic Architecture (Hierarchical):**

| Sheet | Components | Role |
|-------|------------|------|
| **Master** (`Voltage Regulator.kicad_sch`) | — | Links input → regulation → output |
| **Input** (`input.kicad_sch`) | D1–D4: Bridge Rectifier, J1: Screw Terminal | AC/DC input & rectification |
| **Main** (`main.kicad_sch`) | U1: `L7805` Regulator, C1: `2200µF`, C2: `10µF` | Voltage regulation & filtering |
| **Output** (`output.kicad_sch`) | D5: Green LED, R1: `330Ω`, J2: Screw Terminal | Power indicator & output |

**Flat Design Alternative:**
The `Voltage Regulator - Copy/` folder contains the exact same circuit laid out **non-hierarchically on a single flat sheet** for direct visualization of all connections.

**How It Works:** AC input is rectified by the diode bridge, filtered by the `2200µF` reservoir capacitor, and then regulated to a stable +5V by the L7805 linear regulator. The `10µF` output capacitor filters high-frequency transients. A green LED with a `330Ω` resistor provides a visual power-on indicator.

---

## 📊 Project Complexity Matrix

| # | Project | Components | IC Used | Design | Has PCB |
|---|---------|-----------|---------|--------|---------|
| 1 | Bridge Rectifier | 7 | — | Flat | ✅ |
| 2 | Buzzer Alarm | 5 | — | Flat | ✅ |
| 3 | LED Blink (IC555) | 8 | NE555 | Flat | ✅ |
| 4 | LED Circuit | 20+ | — | Flat | ✅ |
| 5 | Low Pass Filter | 3 | — | Flat | ✅ |
| 6 | Metronome | 8+ | 555 Timer | Flat | ✅ |
| 7 | Motor Speed Controller | 12+ | ICM7555 + L293 | Flat | ✅ |
| 8 | Simple LED Circuit | 4 | — | Hierarchical | ✅ |
| 9 | Voltage Divider | 3 | — | Flat | ✅ |
| 10 | Voltage Regulator | 9 | L7805 | Hierarchical | ✅ |

---

## 🧠 Key Concepts Demonstrated

| Concept | Projects |
|---------|----------|
| **AC/DC Rectification** | Bridge Rectifier, Voltage Regulator |
| **555 Timer (Astable Mode)** | LED Blink, Metronome, Motor Speed Controller |
| **Transistor Switching (BJT)** | Buzzer Alarm, LED Circuit |
| **Passive Filters (RC)** | Low Pass Filter |
| **Voltage Regulation** | Voltage Regulator (L7805) |
| **Motor Drive (H-Bridge)** | Motor Speed Controller (L293) |
| **Hierarchical Schematic Design** | Simple LED Circuit, Voltage Regulator |
| **PWM Speed Control** | Motor Speed Controller |

---

## 🚀 Getting Started

### Prerequisites
- **[KiCad 8.0+](https://www.kicad.org/download/)** installed on your system (v10.0 recommended)

### Opening a Project
1. Clone or download this repository:
   ```bash
   git clone https://github.com/yourusername/pcb-internship-projects.git
   ```
2. Open **KiCad** and go to **File → Open Project...**
3. Navigate to any subfolder (e.g., `Motor Speed Controller/`)
4. Select the `.kicad_pro` file to launch the project
5. From the project manager:
   - Double-click `.kicad_sch` → View & edit schematics
   - Double-click `.kicad_pcb` → View PCB layout & routing

### Simulation
Many projects include SPICE simulation models. To simulate:
1. Open the schematic in Eeschema
2. Go to **Inspect → Simulator**
3. Configure and run your simulation

---

## 📜 License

This project is open source and available for educational purposes.

---

<p align="center">
  <strong>Built with ⚡ by <a href="https://selvaux.in">Selva Pandi</a></strong><br/>
  <em>Offline AI · Edge Computing · Embedded Systems · Custom OS</em><br/><br/>
  <sub>✨ The curiosity doesn't stop — neither does the work.</sub>
</p>
