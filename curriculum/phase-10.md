---
title: Phase 10 — Security & Reverse Engineering
parent: Curriculum
nav_order: 14
---

# Phase 10 — Security & Reverse Engineering

## Prerequisites

**Do NOT start this phase without:**
- Phase 2 (Systems in C) — you need to understand memory layout, pointers, stack vs heap
- Phase 1 (Architecture) — you need to read assembly
- Phase 4 (Tools) — you need a working debugger setup

Security without systems knowledge is just memorizing attack names. With systems knowledge, you understand *why* they work.

---

## 📱 Phone Reading

| Resource | Why | Link |
|----------|-----|------|
| OpenSecurityTraining2 | Full RE curriculum, university-quality, free | [→](https://p.ost2.fyi/) |
| How to Secure a Linux Server | Practical security hardening | [→](https://github.com/imthenachoman/How-To-Secure-A-Linux-Server) |
| CTF Field Guide (Trail of Bits) | Learn security through CTF challenges | [→](https://trailofbits.github.io/ctf/) |
| pwn.college | Browser-based binary exploitation practice | [→](https://pwn.college/) |
| exploit.education | Practical exploitation exercises | [→](https://exploit.education/) |

---

## 🎥 Key Videos

- [LiveOverflow — Binary Exploitation series](https://www.youtube.com/playlist?list=PLhixgUqwRTjxglIswKp9mpkfPNfHkzyeN)
- [OpenSecurityTraining2 — Architecture 1001](https://www.youtube.com/playlist?list=PLUFkSN0XLZ-kF1f143wlw8ujlH2A45nZY)
- [John Hammond — CTF walkthroughs](https://www.youtube.com/@_JohnHammond)
- [CS50 Cybersecurity (Harvard)](https://www.youtube.com/watch?v=jkfNtyp_oLU)
- [Low Level Learning — How buffer overflows work](https://www.youtube.com/watch?v=1S0aBV-Waeo)

---

## 🏗 Projects

| Project | Description | Link |
|---------|-------------|------|
| picoCTF | Beginner CTF challenges, browser-based | [→](https://picoctf.org/) |
| pwn.college | Structured binary exploitation practice | [→](https://pwn.college/) |
| Reverse a simple crackme | Find the password in a compiled binary | Search "crackme" on [crackmes.one](https://crackmes.one/) |

---

## Learning Order

1. **Assembly basics** — read x86 before touching tools (OpenSecurityTraining2 Arch 1001)
2. **Debugging in GDB** — Beej's GDB guide, practice on your C projects
3. **Buffer overflows** — LiveOverflow series, then picoCTF binary exploitation track
4. **Reverse engineering** — OpenSecurityTraining2 RE1001, then crackmes

---

## Done when...

You can open a binary in a disassembler, identify the main function, follow the logic, and explain what it does — without source code.
