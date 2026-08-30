<!-- 🚩 FLAG: This is Month 36 of the IW Cyber Ops roadmap. -->

# 👑 Phase V: Advanced Specialization & Independent Research (M36–M42)

## 🎯 7.1 Specialization Track Selection Overview

At Month 36, choose **One Primary Specialization** and **One Secondary Domain**:

| Specialization Track | Core Deep-Dive Focus Areas |
| :--- | :--- |
| **Track A: Browser Research** | Chromium/V8, JavaScriptCore, JIT optimization bugs, Type Confusion, DOM engines, Mojo IPC, Renderer sandbox escapes. |
| **Track B: Kernel Research** | Linux/Windows kernel internals, eBPF, driver IOCTLs, Slab/SLUB allocators, reference-count races, KASLR bypasses. |
| **Track C: Mobile Systems** | Android ART internals, Binder IPC driver, baseband firmware, iOS XNU kernel, Mach messages, sandbox escape chains. |
| **Track D: Firmware & Hypervisors** | UEFI boot chain, SMM exploitation, QEMU device emulation bugs, KVM/VMX boundaries, hardware DMA attacks. |

---

## 📅 Month 36: Specialization Target Architecture & Source Tree Deep Dive

> **🎯 Primary Outcome:** Build, navigate, and architecturally master the complete codebase of your chosen specialization target.

---

### 🧠 1. Theoretical Depth & Core Concepts

*   **Codebase Ingestion:** Compiling the multi-million-line target from source with debug symbols; mapping build configurations (GN, Ninja, CMake, Kbuild).
*   **Architecture Reconstruction:** Mapping input parsing boundaries, IPC interfaces, memory ownership schemes, and privilege boundaries.
*   **Historical Vulnerability Review:** Reading the last 20 CVE fixes and security commits in your specialization target subsystem.

---

### 🛠️ 2. Tools & Operational Environment

`Target Source Repository` | `Clang / GCC` | `GDB / WinDbg / LLDB` | `Ninja / CMake` | `Sourcegraph / OpenGrok`

---

### ⏱️ 3. Step-by-Step 12-Hour Daily Blueprint

*   **Hours 01–04 (Core):** Compile target from source with debug flags; trace subsystem initialization routines in GDB/WinDbg.
*   **Hour 05 (C Track):** Read and annotate 500 lines of complex C/C++ source code directly from the target codebase daily.
*   **Hour 06 (ASM Track):** Dissect compiler-generated assembly for performance-critical functions inside the target.
*   **Hour 07 (Hardware Track):** Study hardware interaction boundaries relevant to the specialization (MMIO, CPU registers, DMA).
*   **Hours 08–10 (Lab):** Build custom target debugging scripts in GDB/WinDbg automating structure printing and memory inspection.
*   **Hour 11 (Reading):** Read historical CVE advisories and root-cause writeups for the chosen specialization.
*   **Hour 12 (Documentation):** Compile the 25+ page Architecture Notebook mapping all subsystems and trust boundaries.

---

### 🚀 4. Concrete Projects & Milestone Deliverables

1.  **Complete Architecture Notebook (25+ Pages):** A detailed technical document mapping subsystems, entry points, and trust boundaries.
2.  **Custom Target Debugging Environment:** Configure dedicated GDB/WinDbg/LLDB scripts automating symbols resolution and structure printing.
3.  **Build System Automation Suite:** Write scripts automating the compilation of instrumented (ASan, coverage) builds of the target.

---

### 📚 5. Primary Learning Sources

*   💻 *Target Official Developer Documentation*
*   💻 *Source Code Repositories*
*   📄 *Historical Security Bulletins and Commit Logs*

---

### 🚧 6. Common Roadblocks & Exact Solutions

> **❌ Error:** Massive target compilation fails after 3 hours due to missing esoteric build dependencies.
>
> **🔍 Root Cause:** Large codebases (e.g., Chromium, Linux Kernel) rely on specific hermetic toolchains and system libraries.
> 
> **✅ Fix:** Use official developer container images (Docker) or follow official `install-build-deps.sh` scripts exactly without deviation.
