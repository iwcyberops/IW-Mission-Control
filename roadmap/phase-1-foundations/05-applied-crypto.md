<!-- 🚩 FLAG: This is Month 5 of the IW Cyber Ops roadmap. -->

# 🛡️ Phase I: Foundations & Systems Architecture (M1–M8)

## 📅 Month 5: Applied Cryptography, Web Foundations & Compilation Pipelines

> **🎯 Primary Outcome:** Understand secure communication channels, web client-server protocols, and the complete source-to-binary compilation process.

---

### 🧠 1. Theoretical Depth & Core Concepts

*   **Applied Cryptography:** Symmetric ciphers (AES-CBC, AES-GCM mechanics, IV reuse risks), Asymmetric cryptography (RSA modular arithmetic, ECC discrete logarithm), Hashing (SHA-256, HMAC, collision resistance), Public Key Infrastructure (PKI), X.509 certificates, TLS 1.3 handshake mechanics.
*   **Web Application Architecture:** HTTP request/response lifecycles, headers, cookies (`Secure`, `HttpOnly`, `SameSite`), CORS, Same-Origin Policy (SOP), DOM tree structures, client-side JavaScript execution models.
*   **Compiler & Linker Internals:** Preprocessing (`cpp`), lexical analysis, syntax parsing, AST generation, assembly code generation, object files (`.o`), relocations, static vs. dynamic linking (`ld.so`), ELF format (Headers, Sections, Segments), Global Offset Table (GOT) and Procedure Linkage Table (PLT) mechanics.

---

### 🛠️ 2. Tools & Operational Environment

`OpenSSL CLI` | `Burp Suite Community` | `Browser DevTools` | `GCC` | `Clang` | `readelf` | `objdump` | `Python Cryptography`

---

### ⏱️ 3. Step-by-Step 12-Hour Daily Blueprint

*   **Hours 01–04 (Core):** Dissect compilation and linking stages; analyze ELF relocation sections (`readelf -r`) and PLT stubs.
*   **Hour 05 (C Track):** Write modular C programs utilizing header files, multi-file compilation, and custom Makefiles.
*   **Hour 06 (ASM Track):** Analyze compiler optimization transformations: loop unrolling, register allocation, inlining.
*   **Hour 07 (Hardware Track):** Study instruction cycles (Fetch, Decode, Execute, Memory, Writeback) and CPU microcode.
*   **Hours 08–10 (Lab):** Build a basic HTTP/1.0 web server in pure C; implement request header parsing and file delivery.
*   **Hour 11 (Reading):** Read *Serious Cryptography* chapters on block ciphers, hash functions, and authenticated encryption.
*   **Hour 12 (Documentation):** Draw the complete execution trace of a dynamically linked library call resolving through PLT and GOT.

---

### 🚀 4. Concrete Projects & Milestone Deliverables

1.  **C HTTP/1.0 Socket Web Server:** Build a multithreaded web server in C parsing HTTP requests and serving static assets.
2.  **Custom Enterprise PKI Lab:** Create a private Root CA, intermediate CA, issue signed certificates, and enforce TLS validation.
3.  **Optimization Disassembly Analysis Report:** Compare identical C functions compiled under `-O0`, `-O2`, and `-Os` with detailed assembly annotations.

---

### 📚 5. Primary Learning Sources

*   📖 *Serious Cryptography* (Jean-Philippe Aumasson)
*   💻 *Cryptopals Crypto Challenges* (Set 1)
*   💻 *PortSwigger Web Security Academy*
*   💻 *GCC Documentation*

---

### 🚧 6. Common Roadblocks & Exact Solutions

> **❌ Error:** Shared library function call fails with relocation `R_X86_64_32S` against `.rodata` can not be used.
>
> **🔍 Root Cause:** Code compiled without Position-Independent Code (PIC) flags cannot be linked into a shared library on 64-bit architectures.
> 
> **✅ Fix:** Compile all shared library object files with the `-fPIC` compiler flag.

<!-- end of month 5 - IW Cyber Ops - -->
