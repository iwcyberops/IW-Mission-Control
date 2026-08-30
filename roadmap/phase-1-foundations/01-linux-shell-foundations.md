<!-- 🚩 FLAG: This is Month 1 of the IW Cyber Ops roadmap. -->

# 🛡️ Phase I: Foundations & Systems Architecture (M1–M8)

## 📅 Month 1: Linux Kernel Interface, Shell Automation, Git & Lab Engineering

> **🎯 Primary Outcome:** Reach complete CLI independence, master the Linux system architecture, and build a reproducible virtual security lab.

---

### 🧠 1. Theoretical Depth & Core Concepts

*   **Filesystem Hierarchy Standard (FHS):** In-depth purpose and security implications of `/etc`, `/var`, `/proc`, `/sys`, `/dev`, `/tmp`, `/opt`.
*   **Text Manipulation & Automation:** Regex filtering with `grep -E`, stream editing with `sed`, data extraction pipelines using `awk`, sorting, deduplication, `xargs` parallel execution.
*   **Process Model & Signals:** PID, PPID, process lifecycles, systemd units, standard UNIX signals (`SIGTERM`, `SIGKILL`, `SIGSEGV`, `SIGINT`, `SIGUSR1`).
*   **Permissions & Security Boundaries:** DAC (Discretionary Access Control), UID/GID, SUID/SGID execution mechanics, Sticky bit, `umask` calculation, `sudoers` syntax and execution flags.
*   **Version Control Plumbing:** Git internals (`objects`, `refs`, `HEAD`), branching, rebasing, tracking file diffs, inspecting security commits via `git log -p`.

---

### 🛠️ 2. Tools & Operational Environment

`Kali Linux` | `Debian / Ubuntu Server LTS` | `VMware Workstation Pro / VirtualBox` | `bash` | `tmux` | `vim` | `git` | `strace` | `lsof` | `htop`

---

### ⏱️ 3. Step-by-Step 12-Hour Daily Blueprint

*   **Hours 01–04 (Core):** Study Linux system architecture, FHS, process management, and DAC permissions models.
*   **Hour 05 (C Track):** Write basic C programs; master compilation stages: `gcc -E`, `gcc -S`, `gcc -c`, `gcc -o`.
*   **Hour 06 (ASM Track):** Study x86-64 General Purpose Registers (`RAX`, `RBX`, `RCX`, `RDX`, `RSI`, `RDI`, `RSP`, `RBP`).
*   **Hour 07 (Hardware Track):** Learn Ohm’s Law, Kirchhoff’s Laws, voltage, current, resistance, and discrete logic gates.
*   **Hours 08–10 (Lab):** Build an isolated dual-NIC lab in VMware; write modular Bash monitoring scripts; solve OverTheWire Bandit.
*   **Hour 11 (Reading):** Read official Linux man pages (`man 2 fork`, `man 2 execve`, `man 5 sudoers`).
*   **Hour 12 (Documentation):** Maintain your Markdown research journal; document lab topology diagrams with Git commits.

---

### 🚀 4. Concrete Projects & Milestone Deliverables

1.  **Automated Lab Deployment Engine:** Write a Bash automation suite deploying an isolated network containing Kali and a victim VM.
2.  **System Artifact Scanner:** A Bash tool scanning for world-writable directories, SUID binaries, and non-standard processes.
3.  **Git-Powered Research Repository:** Initialize and structure your multi-year security research documentation repository.

---

### 📚 5. Primary Learning Sources

*   📖 *How Linux Works: What Every Superuser Should Know* (Brian Ward)
*   📖 *The Linux Command Line* (William Shotts)
*   💻 *OverTheWire* Bandit Wargames
*   💻 *pwn.college* Linux Luminarium

---

### 🚧 6. Common Roadblocks & Exact Solutions

> **❌ Error:** SUID script execution does not grant root privileges.
>
> **🔍 Root Cause:** Linux kernels ignore SUID bits on interpreted shell scripts for security reasons.
> 
> **✅ Fix:** Compile a small C wrapper binary that calls `setuid(0)` and `execve()` to trigger SUID execution legitimately.
