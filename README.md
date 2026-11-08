# Design-and-Simulation-of-a-Low-Power-6T-SRAM-Cell-Using-Power-Gating-Technique-in-Cadence-Virtuoso
Design and simulation of a low-power 6T SRAM cell using Power-Gating in Cadence Virtuoso. Implemented with PMOS header and NMOS footer sleep transistors, achieving **39.97% average power reduction** through low-power VLSI design techniques.

# Design and Simulation of a Low-Power 6T SRAM Cell Using Power-Gating Technique in Cadence Virtuoso

## 1. Project Overview

Static Random Access Memory (SRAM) is widely used in digital systems, processors, microcontrollers, and embedded applications because of its high-speed data access. However, conventional SRAM cells consume static power even during standby conditions due to leakage current.

This project focuses on designing and simulating a **low-power 6T SRAM cell using the Power-Gating technique** in Cadence Virtuoso. A PMOS header and an NMOS footer sleep transistor are integrated into the conventional 6T SRAM architecture to control the power supply during active and sleep modes.

The design is implemented at transistor level and simulated using the Spectre simulator. The performance is evaluated through transient analysis and average power measurements.

## 2. Project Objectives

- Design a conventional 6T SRAM cell using CMOS transistors.
- Integrate PMOS header and NMOS footer sleep transistors.
- Implement active and sleep operating modes.
- Analyse SRAM storage-node behaviour (Q and QB).
- Observe the virtual supply voltage and sleep-control signals.
- Compare power consumption in active and sleep modes.
- Evaluate the effectiveness of power gating in reducing power consumption.

## 3. Proposed Architecture

The proposed design consists of:

- **6T SRAM Cell:** Two PMOS pull-up transistors, two NMOS pull-down transistors, and two NMOS access transistors.
- **PMOS Header Transistor:** Controls the connection between the actual supply voltage (VDD) and virtual supply voltage (VDDV).
- **NMOS Footer Transistor:** Controls the connection between virtual ground and actual ground.
- **Sleep Control Circuit:** Generates the control signals required to switch between active and sleep modes.

The internal storage nodes Q and QB maintain complementary logic values, while WL, BL, and BLB control the access and write operations.

## 4. Working Principle

### Active Mode
- Both header and footer sleep transistors are ON.
- The SRAM cell receives the required supply voltage.
- Normal read, write, and hold operations are supported.
- The virtual supply voltage remains close to the nominal supply voltage of 1.8 V.

### Sleep Mode
- Both sleep transistors are switched OFF.
- The SRAM circuit is isolated from the supply network.
- The supply current and power consumption are reduced.

**Note:** Data retention during complete power isolation requires separate verification and is considered future work.

## 5. Tools and Technologies

| Category | Technology |
|---|---|
| Design Software | Cadence Virtuoso |
| Circuit Simulator | Spectre |
| Analysis | Transient Analysis |
| Power Measurement | Cadence ADE Calculator |
| Design Level | Transistor-Level CMOS |
| Supply Voltage | 1.8 V |
| Temperature | 27 °C |
| Simulation Time | 100 ns |

## 6. Implementation and Simulation

The project was implemented using the following workflow:

1. Design the conventional 6T SRAM cell in Cadence Virtuoso.
2. Integrate the PMOS header and NMOS footer sleep transistors.
3. Configure the sleep-control signals S and SB.
4. Develop the test bench with supply voltage, word line, bit lines, and control signals.
5. Perform transient analysis using the Spectre simulator.
6. Observe Q, QB, WL, BL, BLB, sleep-control signals, and virtual supply voltage.
7. Measure average power using the Cadence ADE Calculator.
8. Compare active-mode and sleep-mode power measurements.

## 7. Simulation Results

The simulation was performed at a supply voltage of 1.8 V and a temperature of 27 °C over a 100 ns interval.

### Active Mode vs Sleep Mode

| Parameter | Active Mode | Sleep Mode |
|---|---:|---:|
| Average Power | 942.892 nW | 565.992 nW |
| Sleep-Transistor Power | 16.555 nW | 352.004 pW |

### Key Results

- **Average Power Reduction:** 39.97%
- **Sleep-Transistor Power Reduction:** 97.87%
- **Virtual Supply Voltage:** Approximately 1.8 V during the observed active-mode operation.
- **Transient Response:** Storage-node voltages and virtual supply behaviour were analysed.

### Result Analysis

The average power decreases from 942.892 nW to 565.992 nW between the active-mode and sleep-mode simulation runs.

The power dissipated in the sleep transistor decreases from 16.555 nW to 352.004 pW, representing a reduction of approximately 97.87%.

These measurements demonstrate the potential of power gating to reduce power consumption. However, the complete standby-power saving requires further evaluation of steady-state sleep conditions and all supply paths.

## 8. Advantages

- Reduces power consumption during sleep mode.
- Helps minimise leakage current.
- Supports active and sleep mode control.
- Can be integrated with the conventional 6T SRAM architecture.
- Improves energy efficiency during idle periods.
- Suitable for low-power VLSI and embedded applications.

## 9. Limitations

- Additional sleep transistors increase circuit area.
- Sleep-control circuitry increases design complexity.
- Sleep-transistor ON resistance may cause voltage drop.
- Wake-up delay may occur when returning to active mode.
- Data retention during sleep has not been verified.
- The design is limited to transistor-level simulation of a single SRAM cell.
- Full memory-array implementation and post-layout verification are not included.

## 10. Future Scope

- Verify data retention during sleep and wake-up operations.
- Analyse static noise margin during read, write, and hold operations.
- Measure wake-up time and in-rush current.
- Optimise sleep-transistor sizing.
- Perform process-corner, voltage, and temperature analysis.
- Implement layout design and post-layout simulation.
- Extend the design to a complete SRAM memory array.

## 11. Repository Contents

- `LPVD_AAT_Report_Final (1).pdf` – Complete project report.
- `README.md` – Project overview, implementation details, and simulation results.
- `Screenshot 2026-11-08 203628.png` – Project simulation screenshot.
- `Screenshot 2026-11-08 204815.png` – Project simulation screenshot.
- `Screenshot 2026-11-08 205002.png` – Test bench configuration screenshot.
- `Screenshot 2026-11-08 205142.png` – Project simulation screenshot.
- `Screenshot 2026-11-08 205316.png` – Project simulation screenshot.
- `Screenshot 2026-11-08 205539.png` – Project simulation screenshot.
- `Screenshot 2026-11-08 205704.png` – Project simulation screenshot.

## 12. Conclusion

This project demonstrates the design and simulation of a power-gated 6T SRAM cell using Cadence Virtuoso. By integrating PMOS header and NMOS footer sleep transistors, the design enables active and sleep mode operation.

The simulation results show a 39.97% reduction in average power and a 97.87% reduction in sleep-transistor power between the measured active-mode and sleep-mode runs. The work provides practical exposure to CMOS circuit design, power-gating techniques, transient analysis, and low-power VLSI design.

---

**Project Domain:** VLSI Design | Low-Power CMOS | SRAM Design

**Tools Used:** Cadence Virtuoso | Spectre Simulator

**Key Technologies:** 6T SRAM | Power Gating | Sleep Transistors | CMOS
