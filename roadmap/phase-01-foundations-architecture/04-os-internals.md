<!-- 🚩 FLAG: This is Month 4 of the IW Cyber Ops roadmap. -->

# 🛡️ Phase I: Foundations & Systems Architecture (M1–M8)

## 📅 Month 4: OS Internals, Virtual Memory, Process Management & C Memory

> **🎯 Primary Outcome:** Understand the boundary between source code, virtual process memory, CPU execution rings, and operating system kernels.

---

### 🧠 1. Theoretical Depth & Core Concepts

*   **Privilege Separation:** Kernel Space (Ring 0) vs. User Space (Ring 3), Context switching, Hardware Interrupts, System Call transition mechanics.
*   **Virtual Memory Architecture:** Multi-level Page Tables, Page Directories, Translation Lookaside Buffer (TLB), Virtual-to-Physical address translation, Memory Management Unit (MMU), demand paging, swapping.
*   **Process Memory Layout:** Text (executable code), Data (initialized globals), BSS (uninitialized globals), Heap (dynamic allocation growing up), Stack (call frames growing down).
*   **System Calls & IPC:** File descriptors, `fork()`, `vfork()`, `execve()`, `waitpid()`, anonymous pipes, FIFOs, POSIX shared memory.
*   **Dynamic Memory Management in C:** Internals of `malloc()`, `calloc()`, `realloc()`, `free()`, pointer lifetime, dangling pointers, undefined behavior.

---

### 🛠️ 2. Tools & Operational Environment

`GDB with Pwndbg` | `strace` | `ltrace` | `pmap` | `readelf` | `objdump` | `Valgrind` | `GCC`

---

### ⏱️ 3. Step-by-Step 12-Hour Daily Blueprint

*   **Hours 01–04 (Core):** Dissect virtual address spaces; inspect `/proc/[pid]/maps`, trace syscalls with `strace`.
*   **Hour 05 (C Track):** Implement custom memory allocation wrapper with metadata tracking for buffer allocations.
*   **Hour 06 (ASM Track):** Analyze how the stack frame is initialized: `push rbp; mov rbp, rsp; sub rsp, N`.
*   **Hour 07 (Hardware Track):** Study CPU memory buses, memory hierarchies, SRAM vs. DRAM, and cache mapping techniques.
*   **Hours 08–10 (Lab):** Write a UNIX process supervisor in C that handles `fork()`, `execve()`, and signal handling.
*   **Hour 11 (Reading):** Read *CS:APP* Chapter 9 (Virtual Memory) thoroughly.
*   **Hour 12 (Documentation):** Draw a step-by-step diagram of 4-level Page Table Translation on x86-64 systems.

---

### 🚀 4. Concrete Projects & Milestone Deliverables

1.  **Custom UNIX Command Shell in C:** Fully functional mini-shell supporting execution, argument parsing, pipes, and I/O redirection.
2.  **Process Memory Map Extractor:** A C utility that reads `/proc/[pid]/maps` and dumps memory segments for live processes.
3.  **Memory Leak Profiling Report:** Profile a complex C program using Valgrind, identifying heap leaks and uninitialized pointer reads.

---

### 📚 5. Primary Learning Sources

*   📖 *Computer Systems: A Programmer's Perspective (CS:APP)* (Bryant & O'Hallaron)
*   📖 *The Linux Programming Interface* (Michael Kerrisk)

---

### 🚧 6. Common Roadblocks & Exact Solutions

> **❌ Error:** Program crashes with `Segmentation fault (core dumped)` when writing to dynamic memory.
>
> **🔍 Root Cause:** Attempting to write to read-only memory segments (e.g., string literal in `.rodata`) or accessing unmapped virtual pages.
> 
> **✅ Fix:** Allocate modifiable heap memory using `malloc()` or allocate stack arrays, and verify pointer bounds with GDB.
