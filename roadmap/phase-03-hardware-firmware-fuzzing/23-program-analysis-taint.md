<!-- 🚩 FLAG: This is Month 23 of the IW Cyber Ops roadmap. -->

# ⚡ Phase III: Hardware, Firmware, Advanced Fuzzing & Systems (M19–M27)

## 📅 Month 23: Advanced Program Analysis – CFG, SSA, Data-Flow & Taint Tracking

> **🎯 Primary Outcome:** Understand how static and dynamic program analysis algorithms reason about software binaries without execution.

---

### 🧠 1. Theoretical Depth & Core Concepts

*   **Intermediate Representations (IR):** Lifting machine code to IR (LLVM IR, Ghidra P-Code, angr VEX), Control Flow Graphs (CFG), Call Graphs.
*   **Static Analysis Concepts:** Static Single Assignment (SSA) form, Use-Def chains, Reaching definitions, Abstract Interpretation.
*   **Taint Analysis:** Source-Sink models, tracking untrusted user input flow across memory and registers to sensitive execution sinks.
*   **Dynamic Binary Instrumentation (DBI):** Basic block counting, instruction tracing, memory access profiling via DBI frameworks (Frida, Intel PIN).

---

### 🛠️ 2. Tools & Operational Environment

`Ghidra P-Code` | `angr` | `LLVM Opt` | `Frida Stalker` | `Intel PIN / DynamoRIO`

---

### ⏱️ 3. Step-by-Step 12-Hour Daily Blueprint

*   **Hours 01–04 (Core):** Dissect LLVM IR and Ghidra P-Code; write automated static analysis scripts searching for taint paths.
*   **Hour 05 (C Track):** Implement custom Abstract Syntax Tree (AST) walkers in C/C++ using Clang LibTooling.
*   **Hour 06 (ASM Track):** Analyze binary control-flow flattening obfuscation; identify dispatch blocks and state variables.
*   **Hour 07 (Hardware Track):** Study hardware debugging registers (`DR0–DR7`) and execution breakpoint architecture.
*   **Hours 08–10 (Lab):** Write a custom LLVM analysis pass identifying potential integer overflow vulnerabilities at compile time.
*   **Hour 11 (Reading):** Read *Compilers: Principles, Techniques, and Tools (Dragon Book)* chapters on Data-Flow Analysis.
*   **Hour 12 (Documentation):** Draw detailed Control Flow Graphs (CFG) and SSA variable definition charts for analyzed functions.

---

### 🚀 4. Concrete Projects & Milestone Deliverables

1.  **Static P-Code Taint Tracker in Ghidra:** Write a Python script in Ghidra checking if untrusted arguments reach `system()` or `strcpy()`.
2.  **LLVM Custom Analysis Pass:** Write a C++ LLVM pass identifying integer conversions susceptible to sign-extension bugs.
3.  **DBI Instruction Tracer:** Use Frida Stalker or Intel PIN to dynamically log every executed instruction during an authentication check.

---

### 📚 5. Primary Learning Sources

*   📖 *Compilers: Principles, Techniques, and Tools* (Aho, Lam, Sethi, Ullman)
*   💻 *LLVM Language Reference Manual*
*   💻 *Ghidra P-Code Guide*

---

### 🚧 6. Common Roadblocks & Exact Solutions

> **❌ Error:** Static taint analysis reports massive numbers of false positives due to pointer aliasing.
>
> **🔍 Root Cause:** Inability of naive static analyzers to resolve which memory location a pointer refers to across function calls.
> 
> **✅ Fix:** Implement field-sensitive and context-sensitive alias analysis algorithms, or combine static taint tracking with dynamic verification.
