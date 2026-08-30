<!-- 🚩 FLAG: This is Month 37 of the IW Cyber Ops roadmap. -->

# 👑 Phase V: Advanced Specialization & Independent Research (M36–M42)

## 📅 Month 37: Source Code Deep Dive & Subsystem Attack Surface Analysis

> **🎯 Primary Outcome:** Line-by-line manual code audit of selected high-value subsystems in your specialization target.

---

### 🧠 1. Theoretical Depth & Core Concepts

*   **Subsystem Isolation:** Select 2–4 complex, security-critical modules (e.g., JIT compiler optimization passes, network driver packet handling, or Binder IPC serializers).
*   **Data-Flow Tracing:** Manually tracing untrusted user input from ingestion point through every validation function to memory operations.
*   **Hypothesis Formation:** Formulating specific vulnerability hypotheses based on architectural complexity, concurrency, or type casting.

---

### 🛠️ 2. Tools & Operational Environment

`VS Code with C/C++ Extensions` | `Ghidra` | `GDB / WinDbg` | `Clang LibTooling`

---

### ⏱️ 3. Step-by-Step 12-Hour Daily Blueprint

*   **Hours 01–04 (Core):** Perform line-by-line manual code review of the isolated subsystem; map every memory allocation and pointer cast.
*   **Hour 05 (C Track):** Implement small standalone mockups of complex target algorithms in C to test edge-case behavior.
*   **Hour 06 (ASM Track):** Dissect assembly generated for critical validation checks in the subsystem to verify optimization safety.
*   **Hour 07 (Hardware Track):** Study memory bus transactions and hardware caching effects on the target subsystem.
*   **Hours 08–10 (Lab):** Write custom test drivers that feed crafted inputs directly into the isolated subsystem APIs.
*   **Hour 11 (Reading):** Read academic papers and research blogs analyzing vulnerability patterns in the chosen subsystem.
*   **Hour 12 (Documentation):** Maintain a comprehensive Attack Surface Catalog documenting every input sink and hypothesis.

---

### 🚀 4. Concrete Projects & Milestone Deliverables

1.  **Source-Level Attack Surface Catalog:** Comprehensive documentation of all entry points, parsers, and exposed interfaces in the subsystem.
2.  **Custom Static Verification Script:** Write a customized Semgrep/CodeQL or AST analyzer tailored to the target’s unique API patterns.
3.  **Standalone Subsystem Mock Harness:** Build an isolated test framework compiling the target subsystem independently for rapid testing.

---

### 📚 5. Primary Learning Sources

*   💻 *Target Source Code Tree*
*   📜 *Developer Mailing Lists*
*   📜 *Architecture Whitepapers and Specification RFCs*

---

### 🚧 6. Common Roadblocks & Exact Solutions

> **❌ Error:** Tracing data flow becomes impossible due to deeply nested macro definitions and indirect callback dispatches.
>
> **🔍 Root Cause:** Heavy use of C preprocessor macros and dynamic event loops obscures direct call graphs.
> 
> **✅ Fix:** Run `gcc -E` / `clang -E` to generate preprocessed source files, and use dynamic GDB breakpoint logging to trace runtime callbacks.
