# Simple RISC Pipelined Processor

## 📌 Overview
A **custom 5-stage pipelined Simple RISC processor** implemented in hardware and tested on FPGA. Designed to demonstrate CPU pipeline concepts with a simple custom ISA.

---

## ⚙️ Architecture Overview
Pipeline stages:
1. **Instruction Fetch (IF)** – Fetch instruction from memory.
2. **Instruction Decode (ID)** – Decode instruction, read registers.
3. **Execution (EX)** – Perform ALU/branch operations.
4. **Memory Access (MEM)** – Access data memory.
5. **Write Back (WB)** – Write results to registers.

---

## 🛠️ Cycle-by-Cycle Working
**Cycle 1:**
- PC outputs address to Instruction Memory.
- Instruction fetched into IF/ID register.

**Cycle 2:**
- Fetched instruction is decoded.
- Source registers read.
- PC increments to next address.
- New instruction fetched.

**Cycle 3:**
- ALU executes current decoded instruction (EX stage).
- Next instruction in ID stage.
- Another instruction fetched.

**Cycle 4:**
- If needed, data memory is read/written for EX result.
- ALU working on next instruction.
- Decoding and fetching continue in parallel.

**Cycle 5:**
- Result from MEM stage written to destination register.
- All earlier stages processing other instructions.

**Subsequent Cycles:**
- Processor reaches steady state: every cycle completes one instruction (ideal case).

---

## ⚠️ Precautions
- Correct clock frequency for synchronization.
- Preload memory with valid instructions/data.
- Ensure reset initializes PC and pipeline registers.
- Handle hazards via forwarding/stalling.

---

## 📷 Images

![WhatsApp Image 2025-08-09 at 17 48 41_39520b01](https://github.com/user-attachments/assets/d5a4600d-8930-46d3-a441-969e12acb61e)

---

## 📂 Repository Structure
```
Simple-RISC-Pipelined-Processor/
├── src/
├── testbench/
├── images/
└── README.md
```

---

## 🚀 How to Run
1. Clone repo.
2. Open in Xilinx Vivado/ModelSim.
3. Load testbench and run simulation.
4. Implement on FPGA.

---

## 🛠️ Tools Used
- Xilinx Vivado
- ModelSim
- Verilog HDL
- Artix-7 FPGA

---

## ✨ Future Improvements
- Add branch prediction
- Implement cache memory
- Expand ISA
