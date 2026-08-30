<!-- 🚩 FLAG: This is Month 20 of the IW Cyber Ops roadmap. -->

# ⚡ Phase III: Hardware, Firmware, Advanced Fuzzing & Systems (M19–M27)

## 📅 Month 20: Firmware Security II – Bootloaders, Reverse Engineering & Emulation

> **🎯 Primary Outcome:** Extract, unpack, reverse engineer, and emulate embedded operating systems and IoT device firmware.

---

### 🧠 1. Theoretical Depth & Core Concepts

*   **Firmware Architectures:** Monolithic firmware vs. Embedded Linux systems, SquashFS, CramFS, JFFS2, U-Boot environment variables, `bootargs` manipulation.
*   **Static Firmware Extraction:** Binwalk signature scanning, manual magic byte offset carving, extracting filesystems, identifying proprietary encryption/compression.
*   **Firmware Emulation Engineering:** User-mode emulation vs. full-system emulation using QEMU, intercepting NVRAM calls via library hooking (`libnvram.so`), resolving missing hardware peripheral dependencies.
*   **Embedded Vulnerability Discovery:** Hardcoded cryptographic keys, backdoor accounts, insecure web server daemons, embedded command injections.

---

### 🛠️ 2. Tools & Operational Environment

`Binwalk` | `Firmware-Mod-Kit` | `QEMU (qemu-system-arm, qemu-user)` | `Ghidra` | `Firmadyne` | `GDB-multiarch`

---

### ⏱️ 3. Step-by-Step 12-Hour Daily Blueprint

*   **Hours 01–04 (Core):** Extract firmware filesystems; emulate ARM/MIPS embedded HTTP servers inside QEMU.
*   **Hour 05 (C Track):** Implement custom NVRAM hooking libraries in C to fake hardware responses during emulation.
*   **Hour 06 (ASM Track):** Reverse engineer MIPS/ARM binaries in Ghidra; analyze branching and function calls without symbols.
*   **Hour 07 (Hardware Track):** Study Flash translation layers (FTL), wear leveling, and NAND/NOR flash memory physics.
*   **Hours 08–10 (Lab):** Discover, reverse engineer, and exploit an embedded vulnerability inside an emulated IoT router daemon.
*   **Hour 11 (Reading):** Read embedded Linux kernel documentation and U-Boot initialization specifications.
*   **Hour 12 (Documentation):** Document firmware attack surface maps and decompiled vulnerability writeups.

---

### 🚀 4. Concrete Projects & Milestone Deliverables

1.  **Full Firmware Emulation Pipeline:** Extract an ARM-based router firmware, emulate its HTTP daemon in QEMU, and attach GDB remotely.
2.  **Firmware Backdoor Implantation:** Unpack an embedded filesystem, insert an administrative backdoor, repack the SquashFS image, and boot it.
3.  **Embedded 0-Day Bug Discovery in Emulated Daemon:** Discover and exploit a memory corruption or command injection bug in an IoT binary.

---

### 📚 5. Primary Learning Sources

*   📖 *Practical IoT Hacking*
*   📜 *Embedded Linux Documentation*
*   💻 *Azeria Labs ARM Basics*
*   💻 *QEMU Official Documentation*

---

### 🚧 6. Common Roadblocks & Exact Solutions

> **❌ Error:** Emulated embedded daemon crashes immediately on startup with NVRAM open error.
>
> **🔍 Root Cause:** The daemon expects physical NVRAM hardware partitions present on the embedded SoC.
> 
> **✅ Fix:** Compile an interceptor shared library (`libnvram.so`) that intercepts `nvram_get()` calls and inject via `LD_PRELOAD`.
