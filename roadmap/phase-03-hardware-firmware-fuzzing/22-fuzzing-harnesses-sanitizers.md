<!-- 🚩 FLAG: This is Month 22 of the IW Cyber Ops roadmap. -->

# ⚡ Phase III: Hardware, Firmware, Advanced Fuzzing & Systems (M19–M27)

## 📅 Month 22: Fuzzing I – Coverage-Guided Fuzzing, Sanitizers & Harness Design

> **🎯 Primary Outcome:** Treat fuzzing as a disciplined software engineering methodology; build high-performance harnesses, instrument code, and triage crashes.

---

### 🧠 1. Theoretical Depth & Core Concepts

*   **Fuzzing Paradigms:** Black-box, Grey-box, White-box; Generation vs. Mutation-based fuzzing; Evolutionary algorithms and coverage metrics.
*   **Coverage Instrumentation:** Compile-time instrumentation (AFL++ bitmap, edge coverage), trace-pc-guard mechanics, deferred forkserver mechanics.
*   **Harness Engineering:** Writing fast, deterministic, memory-leak-free `LLVMFuzzerTestOneInput` harnesses for target libraries.
*   **Sanitizers:** AddressSanitizer (ASan shadow memory mechanics), UndefinedBehaviorSanitizer (UBSan), MemorySanitizer (MSan), ThreadSanitizer (TSan).
*   **Crash Triage & Minimization:** Deduplication via stack hashes, crash minimization with `afl-tmin`, determining exploitability primitives.

---

### 🛠️ 2. Tools & Operational Environment

`AFL++` | `LLVM LibFuzzer` | `Clang/ASan/UBSan` | `GDB` | `Crashwalk` | `afl-cov`

---

### ⏱️ 3. Step-by-Step 12-Hour Daily Blueprint

*   **Hours 01–04 (Core):** Instrument target parsers with Clang and ASan; write optimized LibFuzzer test harnesses.
*   **Hour 05 (C Track):** Implement custom memory allocation trackers inside fuzz harnesses to eliminate memory leaks.
*   **Hour 06 (ASM Track):** Analyze compiled edge coverage instrumentation assembly stubs injected by AFL++.
*   **Hour 07 (Hardware Track):** Study hardware performance counters and processor branch trace mechanisms (Intel PT).
*   **Hours 08–10 (Lab):** Launch an AFL++ fuzzing campaign against an open-source parser; triage crashes with AddressSanitizer.
*   **Hour 11 (Reading):** Read *The Fuzzing Book* chapters on Coverage-Guided Fuzzing and Mutation Algorithms.
*   **Hour 12 (Documentation):** Document crash triage reports with complete stack traces, shadow memory bytes, and root-cause analyses.

---

### 🚀 4. Concrete Projects & Milestone Deliverables

1.  **High-Performance LibFuzzer Harness for Target Parser:** Write a LibFuzzer harness for an open-source parser achieving >1500 execs/sec.
2.  **Automated AFL++ Fuzzing Pipeline:** Build a script that instruments a target with ASan, runs a dictionary-guided campaign, and logs crashes.
3.  **Sanitizer Crash Root-Cause Report:** Isolate a heap-buffer-overflow crash, analyze its ASan shadow memory report, and write a functional C patch.

---

### 📚 5. Primary Learning Sources

*   💻 *AFL++ Official Documentation*
*   💻 *LLVM LibFuzzer Documentation*
*   📖 *The Fuzzing Book* (Zeller et al.)
*   💻 *Google Sanitizers Wiki*

---

### 🚧 6. Common Roadblocks & Exact Solutions

> **❌ Error:** LibFuzzer harness performance drops below 50 execs/sec.
>
> **🔍 Root Cause:** The harness performs heavy disk I/O, process spawning, or suffers from severe memory leaks across iterations.
> 
> **✅ Fix:** Pass data directly via memory buffers, eliminate file writes, and compile with LeakSanitizer (LSan) to fix memory leaks.
