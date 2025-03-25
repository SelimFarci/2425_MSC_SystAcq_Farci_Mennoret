# ⚙️ Embedded Motor Control Project – STM32G474RE

> ENSEA – MSC Practical Project | 5-Lab Series

This repository contains the full implementation of an embedded motor control system developed over five lab sessions. Based on a **Nucleo-STM32G474RE** microcontroller and a full H-bridge, this project combines UART interfacing, PWM generation, real-time acquisition, and closed-loop control into a complete firmware solution.

---

## 🎯 Project Objectives

From a complete power converter (H-bridge) and a STM32G474RE board, the following features were developed:

- ✅ UART-based command shell (interactive terminal)
- ✅ Complementary phase-shifted PWM generation for 4 transistors
- ✅ Real-time acquisition of analog signals (current, speed, etc.)
- ✅ Implementation of real-time control loops (open-loop and closed-loop)

---

## 📦 Deliverables

- STM32CubeIDE project synchronized with this GitHub repository
- Structured and commented code (HAL + low-level)
- Doxygen documentation for all custom functions
- Project report and source files organized for clarity and reusability

---

## 🛠 Features Overview

### 1. UART Command Shell
- Echo and parsing of commands from terminal (via PuTTY/TeraTerm)
- Supported commands:
  - `help`, `pinout`, `start`, `stop`, `speed XXXX`
- Dynamic command parsing with UART RX interrupt and command buffer

### 2. Complementary PWM Control
- Generation of 4 PWM signals with:
  - Frequency = 20kHz
  - Dead-time insertion
  - 10-bit resolution
- Oscilloscope-verified signal shape and synchronization

### 3. Motor Drive & Open-Loop Control
- Gradual ramp-up of duty cycle to prevent inrush current
- Initial tests at various duty cycles (50%, 70%) with soft start
- MCC motor interfacing & real motor testing

### 4. Current & Speed Acquisition
- Current sensors interfaced via ADC (pooling and DMA)
- Speed measured using encoder + tachymetric analysis
- Timer-triggered ADC/DMA chain for precise sampling

### 5. Control Loop (Closed-Loop Prep)
- Real-time calculation loop for motor current regulation
- Shell-configurable target values (setpoint)
- Scalable architecture for future PI/PID integration

---

## 🧠 Skills & Technologies

| Domain                | Tools & Concepts                            |
|-----------------------|---------------------------------------------|
| Embedded C            | STM32CubeIDE, HAL, timers, interrupts       |
| Control Engineering   | PWM generation, duty cycle ramping          |
| Acquisition Systems   | ADC configuration, DMA, Timer sync          |
| Communication         | UART protocol, command-line shell           |
| Debug & Testing       | Oscilloscope, logic analyzer, GPIO tracing  |
| Documentation         | Doxygen, modular code structure             |

---

## 🧪 Hardware Used
- STM32 Nucleo-G474RE
- Full H-bridge (4 transistor MOSFET)
- DC motor + encoder + load system
- Current sensors, speed sensors (tachometer or incremental)
- UART to USB converter

---

## 📁 Repository Structure
```
2425_MSC_SystAcq_Farci_Selim/
├── Core/                # Application code
├── Drivers/             # HAL + device drivers
├── Inc/                 # Header files
├── Src/                 # Source files
├── Doxygen/             # Auto-generated documentation
├── README.md            # This file
└── .ioc                 # STM32CubeMX config file
```

---

## 👨‍💻 Authors

- **Selim Farci** – Embedded Systems Engineering Student @ ENSEA  
- **Loïc Mennoret** – Embedded Systems Engineering Student @ ENSEA  
- **Nicolas Papazoglou** – Project supervisor and academic advisor @ ENSEA



## 🪪 License

Shared under the **MIT License** for educational and non-commercial use.
