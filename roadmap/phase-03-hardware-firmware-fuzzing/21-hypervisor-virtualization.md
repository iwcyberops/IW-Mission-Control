<!-- 🚩 FLAG: This is Month 21 of the IW Cyber Ops roadmap. -->

# ⚡ Phase III: Hardware, Firmware, Advanced Fuzzing & Systems (M19–M27)

## 📅 Month 21: Hypervisor Architecture & Virtualization Security Foundations

> **🎯 Primary Outcome:** Understand hardware-assisted virtualization, hypervisor internal boundaries, and guest-to-host attack surfaces.

---

### 🧠 1. Theoretical Depth & Core Concepts

*   **Hardware Virtualization Extensions:** Intel VMX (VMCS, root vs. non-root operation, VM exits, VM entries), AMD SVM (VMCB).
*   **Hypervisor Architecture:** Type 1 (bare-metal, e.g., Xen, ESXi) vs. Type 2 (hosted, e.g., KVM/QEMU, VMware Workstation).
*   **Guest-to-Host Attack Surface:** Virtual device emulation (virtual NICs, virtual storage controllers, USB emulation), shared memory channels, MMIO/PIO handling.
*   **VM Escape Vulnerability Classes:** Out-of-bounds access in device emulation loops, unvalidated DMA buffers, race conditions in VM exit handlers.

---

### 🛠️ 2. Tools & Operational Environment

`QEMU Source Tree` | `KVM` | `GDB` | `Linux Kernel with KVM support`

---

### ⏱️ 3. Step-by-Step 12-Hour Daily Blueprint

*   **Hours 01–04 (Core):** Study Intel VMX architecture; trace VM exit handlers in the Linux KVM kernel module.
*   **Hour 05 (C Track):** Implement custom virtual hardware device models in C inside the QEMU source tree.
*   **Hour 06 (ASM Track):** Analyze low-level VMX assembly instructions: `VMLAUNCH`, `VMRESUME`, `VMREAD`, `VMWRITE`.
*   **Hour 07 (Hardware Track):** Study Extended Page Tables (EPT) and Second Level Address Translation (SLAT) hardware mechanisms.
*   **Hours 08–10 (Lab):** Build QEMU from source; trace and debug guest-to-host MMIO communications in GDB.
*   **Hour 11 (Reading):** Read *Intel 64 and IA-32 Architectures Software Developer’s Manual* (Volume 3C: System Programming Guide).
*   **Hour 12 (Documentation):** Draw an architectural map of the guest-to-host MMIO boundary and VM exit lifecycle.

---

### 🚀 4. Concrete Projects & Milestone Deliverables

1.  **Custom Virtual Hardware Device in QEMU:** Write a custom C device model inside QEMU with deliberate MMIO registers; interact from Linux guest.
2.  **Dissection of Historical QEMU VM Escape (VENOM):** Reproduce and dissect the VENOM floppy disk controller vulnerability in source code.
3.  **Hypervisor Threat Model Document:** Write an architectural document mapping all input boundaries from a guest VM to the host kernel.

---

### 📚 5. Primary Learning Sources

*   📖 *Intel 64 and IA-32 Architectures Software Developer’s Manual* (Volume 3C)
*   💻 *QEMU Internal Documentation*
*   📄 *Academic Virtualization Papers*

---

### 🚧 6. Common Roadblocks & Exact Solutions

> **❌ Error:** QEMU fails to launch guest VM with KVM: permission denied.
>
> **🔍 Root Cause:** The host user account lacks access rights to the `/dev/kvm` device node.
> 
> **✅ Fix:** Add your user account to the `kvm` group (`sudo usermod -aG kvm $USER`) and verify `/dev/kvm` permissions.
