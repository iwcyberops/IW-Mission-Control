<!-- 🚩 FLAG: This is Month 19 of the IW Cyber Ops roadmap. -->

# ⚡ Phase III: Hardware, Firmware, Advanced Fuzzing & Systems (M19–M27)

## 📅 Month 19: Hardware Security I – Digital Logic, Buses & Hardware Debug Interfaces

> **🎯 Primary Outcome:** Bridge software engineering to physical electronics, analyze hardware interfaces, and dump raw physical memory.

---

### 🧠 1. Theoretical Depth & Core Concepts

*   **Physical Layer Communications:** Logic levels (3.3V, 5V, 1.8V TTL), baud rate calculation, pull-up/pull-down resistors, signal noise, ground references.
*   **Hardware Bus Protocols:** UART (pinout identification via multimeter, TX/RX discovery), SPI (MOSI, MISO, SCK, CS mechanics), I2C (master/slave addressing, SDA, SCL lines), JTAG (boundary scan, Test Access Port [TAP] controller state machine).
*   **Physical Extraction Techniques:** In-circuit serial programming, SPI flash chip dumping using CH341A/Raspberry Pi, logic capture and protocol decoding.

---

### 🛠️ 2. Tools & Operational Environment

`USB Logic Analyzer` | `CH341A SPI Programmer` | `Digital Multimeter` | `FTDI FT232H / Bus Pirate` | `PulseView / Sigrok` | `minicom`

---

### ⏱️ 3. Step-by-Step 12-Hour Daily Blueprint

*   **Hours 01–04 (Core):** Analyze hardware communication captures in PulseView; identify baud rates, SPI clocks, and I2C packets.
*   **Hour 05 (C Track):** Write embedded C code to interface with hardware peripherals via GPIO, SPI, and UART APIs.
*   **Hour 06 (ASM Track):** Dissect MIPS and ARM assembly code extracted from IoT bootloaders.
*   **Hour 07 (Hardware Track):** Study microcontrollers vs. MPUs, memory maps, boot ROMs, and power distribution circuits.
*   **Hours 08–10 (Lab):** Connect to physical IoT hardware via UART; dump firmware from a physical SPI flash memory chip.
*   **Hour 11 (Reading):** Read *The Hardware Hacking Handbook* chapters on Bus Protocols and Flash Memory.
*   **Hour 12 (Documentation):** Document pinout schematics and logic analyzer timing captures in your research journal.

---

### 🚀 4. Concrete Projects & Milestone Deliverables

1.  **Physical UART Bootloader Shell Access:** Locate UART pins on a commercial IoT board, connect via FTDI, and intercept the U-Boot shell.
2.  **Physical SPI Flash Extraction:** Desolder or clip onto an SOIC-8/16 SPI flash chip, extract binary firmware, and verify SHA-256 integrity.
3.  **I2C Bus Protocol Decoding:** Capture I2C traffic between a microcontroller and EEPROM with a logic analyzer; decode transmitted keys.

---

### 📚 5. Primary Learning Sources

*   📖 *The Hardware Hacking Handbook* (Colin O’Flynn & Jasper van Woudenberg)
*   📖 *Practical IoT Hacking* (Fotios Chantzis et al.)

---

### 🚧 6. Common Roadblocks & Exact Solutions

> **❌ Error:** Serial console output over UART displays unreadable gibberish characters.
>
> **🔍 Root Cause:** The baud rate configuration in the serial terminal client does not match the hardware UART clock rate.
> 
> **✅ Fix:** Measure the narrowest pulse width on the TX line using a logic analyzer; calculate $\text{Baud} = \frac{1}{\text{PulseWidth}}$ (e.g., 115200 or 57600).
