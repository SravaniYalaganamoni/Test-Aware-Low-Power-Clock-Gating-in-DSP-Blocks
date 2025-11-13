# Test-Aware Low-Power Clock Gating in DSP Blocks  
**ECE 242 — Digital System Testing and Testable Design**  
**California State University, Fresno**  
**Advisor:** Dr. Reza Raeisi  
**Author:** Sravani Yalaganamoni (301851603)

---

## 📌 Project Overview
This project presents the **design, synthesis, verification, and testability enhancement** of a **7-tap Finite Impulse Response (FIR) filter** with **test-aware low-power clock gating**. The goal is to reduce dynamic power consumption while preserving **100% fault coverage** using scan-based testing.

The complete ASIC design methodology is followed:
- RTL design in Verilog  
- Functional verification in ModelSim  
- Synthesis using Synopsys Design Compiler  
- Scan insertion using Synopsys DFT tools  
- ATPG and fault simulation using Synopsys TetraMAX  
- Post-synthesis simulation  
- Area, power, timing, and fault coverage analysis  

---

## 🎯 Objectives
- Implement a low-power DSP block (FIR filter) using **clock gating**.  
- Ensure **full scan-based testability** using test-mode override.  
- Achieve high performance while minimizing area and power.  
- Validate design using industry-standard EDA tools.

---

## ⚡ Key Features
### ✔ 7-tap FIR Filter Architecture  
- Fully synchronous pipeline  
- 8-bit inputs, expanded output  
- Symmetric MAC structure for hardware efficiency  

### ✔ Test-Aware Clock Gating  
- Gated clock disables inactive datapath  
- Overrides clock gating during **test_mode = 1**  
- Enables controllability/observability during scan testing  

### ✔ ASIC Flow Implementation  
- RTL → Synthesis → DFT → ATPG → Verification  
- Uses **Nangate 45 nm Open Cell Library**

### ✔ 100% Fault Coverage  
- ATPG using TetraMAX  
- Detected all 922 faults  
- Only 9 test patterns required

---

## 🛠 Tools and Technologies
| Category | Tools |
|---------|-------|
| HDL | Verilog |
| Simulation | ModelSim (Intel FPGA Edition) |
| Synthesis | Synopsys Design Compiler |
| DFT / Scan | Synopsys DFT Compiler |
| ATPG | Synopsys TetraMAX |
| Technology Library | Nangate 45 nm Open Cell Library |
| OS / Environment | Apporto Virtual Lab |

---

## 📐 Design Flow
1. **RTL Development**
   - FIR filter written in Verilog
   - Testbench created for functional simulation

2. **RTL Simulation**
   - Verified using ModelSim
   - Observed delay alignment with FIR tap stages

3. **Synthesis (DC Compiler)**
   - Generated gate-level netlist
   - Achieved:
     - **Area:** ~552.48 µm²  
     - **Power:** ~247.8 µW (28.62 µW leakage)  
     - **Timing Slack:** +2.59 ns @ 4 ns clock  

4. **Scan Insertion**
   - Replaced flip-flops with scan-enabled FFs  
   - Added DFT logic ensuring test mode bypasses gating

5. **Post-Synthesis Simulation**
   - Verified gate delays & functional equivalence  

6. **ATPG (TetraMAX)**
   - Stuck-at and transition faults analyzed  
   - **100% coverage** achieved

---

## 📊 Final Results
| Metric | Result |
|--------|--------|
| FIR Filter Type | 7-Tap, Low-Pass |
| Power Consumption | 247.8 µW |
| Leakage Power | 28.62 µW |
| Area | 552.48 µm² |
| Timing Slack | +2.59 ns |
| ATPG Fault Coverage | **100% (922/922 faults)** |
| Test Patterns | 9 |
| CPU Time | 14.04 seconds |

---

## 📁 Repository Structure

