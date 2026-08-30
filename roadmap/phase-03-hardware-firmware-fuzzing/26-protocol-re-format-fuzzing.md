<!-- 🚩 FLAG: This is Month 26 of the IW Cyber Ops roadmap. -->

# ⚡ Phase III: Hardware, Firmware, Advanced Fuzzing & Systems (M19–M27)

## 📅 Month 26: Protocol Reverse Engineering, Parser Security & Format Fuzzing

> **🎯 Primary Outcome:** Infer unknown binary network protocols, dissect complex serialization formats, and engineer grammar-based fuzzers.

---

### 🧠 1. Theoretical Depth & Core Concepts

*   **Protocol Inference:** Deducing packet framing, type-length-value (TLV) encodings, sequence numbers, checksum algorithms, and state machines.
*   **Complex Formats Security:** ASN.1 (BER, DER encodings), Protocol Buffers, MessagePack, PDF format complexity, media containers (MP4, MKV).
*   **Common Parser Vulnerabilities:** Length confusion, integer overflows leading to out-of-bounds allocation, recursive parser stack exhaustion, state-machine de-synchronization.
*   **Grammar-Based Fuzzing:** Defining structural grammars (Protobuf Mutator, custom mutators in AFL++), stateful protocol fuzzing.

---

### 🛠️ 2. Tools & Operational Environment

`Wireshark (Custom Lua Dissectors)` | `Kaitai Struct` | `AFL++ with custom mutator` | `libprotobuf-mutator` | `Scapy`

---

### ⏱️ 3. Step-by-Step 12-Hour Daily Blueprint

*   **Hours 01–04 (Core):** Dissect proprietary binary protocols; write declarative Kaitai Struct format parsers.
*   **Hour 05 (C Track):** Implement custom grammar mutators in C for integration into AFL++ fuzzing pipelines.
*   **Hour 06 (ASM Track):** Reverse engineer network protocol state machines inside proprietary server binaries.
*   **Hour 07 (Hardware Track):** Study hardware serialization protocols (CAN Bus, Modbus) and industrial control interfaces.
*   **Hours 08–10 (Lab):** Build a custom structure-aware fuzzer targeting a complex ASN.1 or media parser.
*   **Hour 11 (Reading):** Read *The Fuzzing Book* chapters on Grammar-Based and Structure-Aware Fuzzing.
*   **Hour 12 (Documentation):** Document protocol state machine transitions and packet structure specifications.

---

### 🚀 4. Concrete Projects & Milestone Deliverables

1.  **Custom Wireshark Lua Protocol Dissector:** Reverse engineer an unknown binary protocol capture and write a Wireshark Lua dissector.
2.  **Kaitai Struct Binary Format Parser:** Write a declarative Kaitai spec parsing a proprietary file format; auto-generate C++ parser code.
3.  **Structure-Aware Grammar Fuzzer:** Implement an AFL++ custom mutator targeting an ASN.1 or complex XML parser.

---

### 📚 5. Primary Learning Sources

*   💻 *Kaitai Struct Documentation*
*   💻 *Wireshark Lua API Guide*
*   📖 *The Fuzzing Book: Grammar-Based Fuzzing*

---

### 🚧 6. Common Roadblocks & Exact Solutions

> **❌ Error:** Fuzzing complex binary file formats results in 99% rejected inputs at the initial checksum verification stage.
>
> **🔍 Root Cause:** Mutation-based fuzzers destroy CRC32/SHA checksums, preventing deep parser exploration.
> 
> **✅ Fix:** Implement an AFL++ post-processing hook or custom mutator that recalculates and patches valid checksums into mutated payloads.
