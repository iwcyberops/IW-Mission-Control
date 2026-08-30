<!-- 🚩 FLAG: This is Month 8 of the IW Cyber Ops roadmap. -->

# 🛡️ Phase I: Foundations & Systems Architecture (M1–M8)

## 📅 Month 8: Systems C Programming, Compiler Internals & Foundation Capstone

> **🎯 Primary Outcome:** Build advanced systems code in C, understand binary structure thoroughly, and complete the Phase I Foundation Capstone.

---

### 🧠 1. Theoretical Depth & Core Concepts

*   **Advanced Systems C:** POSIX threads (`pthreads`), mutex locks, race condition avoidance, condition variables, atomic operations, signal handling, non-blocking sockets.
*   **Binary Layouts & ELF Structure:** Dissecting ELF magic bytes, 64-bit ELF Header, Section Header Table, Program Header Table (Segments vs Sections), Symbol Tables (`.symtab`, `.dynsym`), String Tables (`.strtab`).
*   **Compiler Internals & Code Generation:** Stack alignment requirements (16-byte boundary on x86-64 ABI), red zone mechanics, function inlining, instruction scheduling.
*   **Foundation Synthesis:** Tracing a program from high-level source code, through compiler AST, assembly emission, object file linking, OS loading, virtual memory mapping, syscall execution, to physical CPU execution.

---

### 🛠️ 2. Tools & Operational Environment

`GCC` | `Clang` | `GDB with Pwndbg` | `readelf` | `objdump` | `strace` | `Valgrind` | `AddressSanitizer (ASan)`

---

### ⏱️ 3. Step-by-Step 12-Hour Daily Blueprint

*   **Hours 01–04 (Core):** Implement advanced systems software in C; parse raw ELF headers and manipulate binary files.
*   **Hour 05 (C Track):** Build a multithreaded producer-consumer queue in C using mutexes and condition variables.
*   **Hour 06 (ASM Track):** Trace the x86-64 System V ABI calling convention parameter registers (`RDI`, `RSI`, `RDX`, `RCX`, `R8`, `R9`).
*   **Hour 07 (Hardware Track):** Study CPU instruction pipelining hazards (Structural, Data, Control Hazards) and branch prediction.
*   **Hours 08–10 (Lab):** Construct the Phase I Foundation Capstone: a networked systems server written in C.
*   **Hour 11 (Reading):** Read System V Application Binary Interface (AMD64 Architecture Processor Supplement).
*   **Hour 12 (Documentation):** Finalize the Phase I Capstone Architectural Report; document every abstraction layer.

---

### 🚀 4. Concrete Projects & Milestone Deliverables

1.  **Multithreaded C Network Daemon:** Build a concurrent TCP server in C using a thread pool, non-blocking I/O, and mutex synchronization.
2.  **Custom ELF Header & Symbol Parser in C:** Write a binary tool parsing raw ELF files, dumping sections, symbols, and relocations.
3.  **Phase I Master Capstone Report:** Complete an exhaustive architectural document detailing the full execution lifecycle from source to silicon.

---

### 📚 5. Primary Learning Sources

*   📖 *The Linux Programming Interface* (Michael Kerrisk)
*   📖 *Expert C Programming: Deep C Secrets* (Peter van der Linden)
*   📖 *System V AMD64 ABI Specification*

---

### 🚧 6. Common Roadblocks & Exact Solutions

> **❌ Error:** Multithreaded C program produces inconsistent data corruption under heavy concurrent load.
>
> **🔍 Root Cause:** Data race condition caused by unsynchronized concurrent read/write operations on shared global variables.
> 
> **✅ Fix:** Compile with ThreadSanitizer (`gcc -fsanitize=thread -g`) to pinpoint the exact line of concurrent access, then wrap with `pthread_mutex_t`.
