<!-- 🚩 FLAG: This is Month 3 of the IW Cyber Ops roadmap. -->

# 🛡️ Phase I: Foundations & Systems Architecture (M1–M8)

## 📅 Month 3: Security Automation with Python + Low-Level Track Acceleration

> **🎯 Primary Outcome:** Master Python for offensive tool engineering while establishing deep momentum across C, Assembly, and Hardware tracks.

---

### 🧠 1. Theoretical Depth & Core Concepts

*   **Python Automation Engine:** Object-Oriented Programming (OOP) for tool design, error handling, robust CLI interfaces with `argparse`.
*   **Systems Automation in Python:** Process control via `subprocess` safely, network programming via `socket`, HTTP automation using `requests`, binary packing/unpacking with `struct`.
*   **Low-Level C Track (1h):** Pointer arithmetic, array-pointer duality, structures, unions, memory alignment, padding, `sizeof` mechanics.
*   **Assembly Track (1h):** Arithmetic and logic instructions: `add`, `sub`, `imul`, `and`, `or`, `xor`, `cmp`, `test`, conditional jumps (`jz`, `jnz`, `jg`, `jl`).
*   **Hardware Track (1h):** Sequential logic: RS Latches, D Flip-Flops, Registers, Synchronous Clock signals, Finite State Machines (FSM).

---

### 🛠️ 2. Tools & Operational Environment

`Python 3.12+` | `gcc` | `make` | `gdb` | `nasm` | `VS Code` | `Logisim / Digital Simulator`

---

### ⏱️ 3. Step-by-Step 12-Hour Daily Blueprint

*   **Hours 01–04 (Core):** Master Python socket programming, binary manipulation with `struct`, and multithreaded network workers.
*   **Hour 05 (C Track):** Implement custom string manipulation functions (`my_strlen`, `my_strcpy`, `my_strcat`) using raw pointers.
*   **Hour 06 (ASM Track):** Write small assembly programs with conditional logic and loops; assemble with `nasm` and link with `ld`.
*   **Hour 07 (Hardware Track):** Construct an 8-bit register file and simple program counter circuit in Logisim.
*   **Hours 08–10 (Lab):** Build an asynchronous multi-threaded port scanner and banner grabber in pure Python.
*   **Hour 11 (Reading):** Read *Python Crash Course* chapters on OOP, exceptions, and testing suites.
*   **Hour 12 (Documentation):** Document the internal mechanics of your Python network utility in your research journal.

---

### 🚀 4. Concrete Projects & Milestone Deliverables

1.  **High-Performance Python Port Scanner:** Multi-threaded network reconnaissance tool with timeout handling and JSON output.
2.  **C Memory Data Structure Suite:** Implement a fully dynamic, memory-managed Linked List in pure C with zero memory leaks.
3.  **4-Bit Digital CPU Datapath:** Build a functional ALU, Register File, and Instruction Decoder circuit inside Logisim.

---

### 📚 5. Primary Learning Sources

*   📖 *Python Crash Course* (Eric Matthes)
*   📖 *The C Programming Language* (Brian Kernighan & Dennis Ritchie)
*   💻 *pwn.college* Computing 101

---

### 🚧 6. Common Roadblocks & Exact Solutions

> **❌ Error:** Python script throws `TypeError: can't concat str to bytes` when sending network packets.
>
> **🔍 Root Cause:** Python 3 strictly separates UTF-8 strings from raw byte arrays.
> 
> **✅ Fix:** Explicitly encode strings before socket transmission (`payload.encode('utf-8')`) or use byte literals (`b"GET / HTTP/1.1\r\n"`).
