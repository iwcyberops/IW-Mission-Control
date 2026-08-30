<!-- 🚩 FLAG: This is Month 6 of the IW Cyber Ops roadmap. -->

# 🛡️ Phase I: Foundations & Systems Architecture (M1–M8)

## 📅 Month 6: System Enumeration, Linux Privilege Escalation & Debugging Fundamentals

> **🎯 Primary Outcome:** Move from system administration to systematic host enumeration, exploit Linux permission misconfigurations, and master GDB debugging.

---

### 🧠 1. Theoretical Depth & Core Concepts

*   **System Enumeration Methodology:** Identifying attack surfaces, querying cron jobs, systemd timers, writable configuration files, environment variables, network sockets, active processes.
*   **Linux Privilege Escalation Vectors:** Misconfigured SUID/SGID binaries, Linux POSIX capabilities abuse (`cap_setuid`, `cap_dac_override`), `/etc/sudoers` wildcard abuse, `LD_PRELOAD` / `LD_LIBRARY_PATH` exploitation, PATH environment variable hijacking, NFS root squashing misconfigurations.
*   **Post-Exploitation Fundamentals:** Spawning interactive TTY shells, reverse vs. bind shells, persistence via SSH keys and cron, secure artifact cleanup.
*   **Low-Level Debugging Mechanics with GDB:** Setting software breakpoints (`int 3`), hardware watchpoints, inspecting memory layouts (`x/32gx`), dereferencing registers, analyzing call stacks (`backtrace`).

---

### 🛠️ 2. Tools & Operational Environment

`GDB with Pwndbg / GEF` | `LinPEAS` | `pspy` | `John the Ripper` | `Hashcat` | `netcat` | `socat` | `chisel`

---

### ⏱️ 3. Step-by-Step 12-Hour Daily Blueprint

*   **Hours 01–04 (Core):** Systematic host enumeration and exploitation of Linux permission models in vulnerable virtual machines.
*   **Hour 05 (C Track):** Implement custom POSIX file permission modification tools and process execution wrappers.
*   **Hour 06 (ASM Track):** Trace program control flow inside GDB using `stepi`, `nexti`, and register inspections.
*   **Hour 07 (Hardware Track):** Study memory bus protocols and hardware timer interrupts driving OS preemptive scheduling.
*   **Hours 08–10 (Lab):** Solve vulnerable Linux privilege escalation rooms on TryHackMe and Hack The Box.
*   **Hour 11 (Reading):** Read POSIX Capabilities documentation (`man 7 capabilities`) and Sudoers manual (`man 5 sudoers`).
*   **Hour 12 (Documentation):** Write detailed pentest-style reports for every machine compromised during lab sessions.

---

### 🚀 4. Concrete Projects & Milestone Deliverables

1.  **Vulnerable Privilege Escalation VM:** Build a custom Debian VM containing 8 deliberate privilege escalation misconfigurations.
2.  **Automated Linux Security Audit Script:** Write a Python tool checking for misconfigured capabilities, sudo rules, and weak file permissions.
3.  **Privilege Escalation Casebook:** Document root acquisition methodologies across 10 vulnerable machines with full root-cause analysis.

---

### 📚 5. Primary Learning Sources

*   💻 *TryHackMe* Linux Privilege Escalation Path
*   💻 *Hack The Box* Easy Linux Track
*   💻 *pwn.college* Privilege Escalation
*   💻 *GDB Documentation*

---

### 🚧 6. Common Roadblocks & Exact Solutions

> **❌ Error:** Privilege escalation script fails because the shell drops elevated privileges instantly upon execution.
>
> **🔍 Root Cause:** Modern bash automatically drops SUID privileges and reverts to the real UID when invoked.
> 
> **✅ Fix:** Pass the `-p` flag to bash (`bash -p`) to prevent it from resetting effective SUID privileges.
