# Fluxara-public

# 🚀 Fluxara — Open Silicon Journey (RTL → GDS → Caravel Integration)

---

## 🧠 Overview

**Fluxara** is an end-to-end open-source ASIC project demonstrating a complete digital design flow:

> **RTL → Synthesis → Floorplan → Placement → Routing → LVS → Tapeout → Caravel Integration**

Built using the **OpenLane + Sky130 PDK** ecosystem, Fluxara represents a **fully realized silicon design journey**, culminating in a clean GDS and successful integration into the Caravel framework.

---

## 🎯 Objectives

* Design a synthesizable digital system
* Achieve **DRC-clean and LVS-matched GDS**
* Integrate as a macro into the Caravel SoC harness
* Resolve real-world physical design challenges (PDN, macro placement, IO alignment)
* Document the full engineering journey

---

## ⚙️ Toolchain

| Stage                  | Tool             |
| ---------------------- | ---------------- |
| RTL Design             | Verilog          |
| Synthesis → GDS        | OpenLane         |
| Physical Design Engine | OpenROAD         |
| PDK                    | Sky130 (sky130A) |
| Layout Visualization   | KLayout          |
| LVS/DRC                | Magic + Netgen   |

---

## 🧬 Design Summary

* **Design Name:** Fluxara (derived from `NoETHERXLabs_Abythera_top`)
* **Flow Type:** Fully automated OpenLane flow with iterative tuning
* **Integration Target:** Caravel `user_project_wrapper`
* **Power Domain:** `vccd1 / vssd1`

---

## 📊 Final Results

| Metric              | Status       |
| ------------------- | ------------ |
| DRC                 | ✅ Clean      |
| LVS                 | ✅ Matched    |
| GDS                 | ✅ Generated  |
| Antenna Violations  | ✅ Resolved   |
| Routing             | ✅ Completed  |
| Caravel Integration | ✅ Successful |

---

## 🏁 Project Milestones

### 🔹 RISCV_04 — LVS Debug Phase

* Encountered **LVS mismatches**
* Issues with:

  * Incomplete extraction
  * Incorrect netlist mapping
  * Blackbox handling

---

### 🔹 RISCV_06 — LVS Convergence

* Switched to **minimal netgen script**
* Corrected netlist source:

  * `.pnl.v` → `.nl.v`
* Achieved **near-final LVS alignment**

---

### 🔹 RISCV_07 — Tapeout Completion

* Final **GDS generated**
* Verified in **KLayout**
* Tapeout package created and archived
* Design reached **first complete silicon-ready state**

---

### 🔹 RISCV_08 — Caravel Integration

* Integrated macro into **Caravel wrapper**
* Fixed macro placement using:

  * Correct instance name (`u_top`)
* Ensured alignment with harness expectations

---

### 🔹 RISCV_09 — PDN Closure

* Resolved **power connectivity issues**
* Adjusted:

  * PDN pitch and offsets
  * Macro power hooks (`vccd1`, `vssd1`)
* Achieved **stable power grid integration**

---

## 🧱 Architecture (High-Level)

Fluxara follows a modular RTL architecture:

* Top-level integration module
* Core logic blocks
* Interconnect and control
* IO interface aligned with Caravel

> Detailed RTL is maintained in internal repositories; this public repo focuses on **flow, methodology, and results**.

---

## 🖼️ Layout Preview

> *(Add KLayout screenshot here)*

```
[ Layout Image Placeholder ]
```

---

## 🔌 Caravel Integration

* Integrated into `user_project_wrapper`
* Macro instantiated as `u_top`
* Power domains:

  * `vccd1` (core supply)
  * `vssd1` (ground)
* Verified:

  * Macro placement
  * PDN alignment
  * IO compatibility

---

## 🧪 Verification Strategy

* OpenLane automated checks
* Magic DRC validation
* Netgen LVS comparison
* Visual inspection via KLayout

---

## 📚 Key Learnings

* **LVS issues are often netlist-related, not layout-related**
* Correct **netlist selection** is critical (`.nl.v` vs `.pnl.v`)
* **PDN alignment** is essential for macro-based designs
* Caravel integration requires strict:

  * Naming conventions
  * Power hook matching
* Debugging ASIC flows is **iterative, not linear**

---

## 🚧 Known Limitations

* Limited documentation of internal RTL (intentionally abstracted)
* Single power domain design
* No post-silicon validation (yet)

---

## 🔮 Future Work

* Multi-domain power design
* Expanded peripheral set
* Post-silicon testbench development
* MPW submission readiness enhancements

---

## 🧑‍💻 Company

**NoETHERXLabs**
Open Silicon Initiative

---

## 🧑‍💻 ENGINEER 
**Jairus Samraj Solomon**

---

## 📜 License

*(Add appropriate open-source license here — e.g., Apache 2.0 / MIT)*

---

## ⭐ Final Note

Fluxara is not just a design — it is a **demonstration of full-stack ASIC capability**:

> From HDL to physical silicon, through real-world constraints, debugging, and integration.
Complete RTL , Flow Code and Logs , GDSII  
<https://github.com/NoETHERXLabs/Fluxara>
---
 
