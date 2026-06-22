---
title: Phase 5 — Operating Systems
parent: Curriculum
nav_order: 9
---

# Phase 5 — Operating Systems

## Why This Phase Exists

This is the gap between "how a CPU works" (Phase 2) and "write C code" (Phase 3). Without it, your C skills float in a vacuum — you write programs without understanding what's actually running them. The OS is the translation layer between your code and the hardware. It's also the foundation for understanding Arch Linux at a meaningful depth.

**Prerequisites:** Phase 2 (Architecture) and Phase 3 (C) — ideally started together. You don't need to finish Phase 3 to start this phase, but you need to be comfortable with C pointers.

---

<details open>
<summary><strong>🎯 Layer 0 — Must Do</strong></summary>

## 📱 Phone Reading

| Resource | Why | Link |
|----------|-----|------|
| OSTEP — Operating Systems: Three Easy Pieces | Free online. One of the best CS textbooks written in any field. Three parts: Virtualization, Concurrency, Persistence. | [→](https://pages.cs.wisc.edu/~remzi/OSTEP/) |

## Reading Order (OSTEP)

| Chapter Group | Topic | Sessions |
|---------------|-------|---------|
| Ch 1–6 | Processes, scheduling | 4 phone sessions |
| Ch 7–9 | Memory virtualization intro | 3 phone sessions |
| Ch 13–16 | Address spaces, paging | 4 phone sessions |
| Ch 26–29 | Concurrency: threads, locks | 4 phone sessions |
| Ch 36–40 | Persistence: file systems | 3 phone sessions |

**Done when Layer 0 complete:** You can explain what a process is, how virtual memory works, what a system call does, and what happens when you `open()` a file.

</details>

---

<details>
<summary><strong>📖 Layer 1 — Go Deeper</strong> &nbsp;(build a mini OS)</summary>

## 🏗 Project — xv6 (MIT teaching OS)

xv6 is a small, clean re-implementation of Unix in C. Reading and modifying it is the "nand2tetris for operating systems."

| Resource | Link |
|----------|------|
| xv6 source code | [→](https://github.com/mit-pdos/xv6-public) |
| xv6 book (free PDF) | [→](https://pdos.csail.mit.edu/6.S081/2020/xv6/book-riscv-rev1.pdf) |
| MIT 6.S081 labs (xv6-based) | [→](https://pdos.csail.mit.edu/6.S081/2020/labs/) |

Start with the labs — they walk you through adding specific features to xv6, which is more guided than reading the source cold.

## 🎥 Key Videos

- [MIT 6.S081 Lectures (2020)](https://www.youtube.com/playlist?list=PLTsf9UeqkReZHXWY9yJvTwLJWYYPcKEqK) — the lectures that accompany the xv6 labs

</details>

---

<details>
<summary><strong>🔬 Layer 2 — Deep Dive</strong> &nbsp;(Linux kernel internals)</summary>

| Resource | Why | Link |
|----------|-----|------|
| Linux Kernel Development (Robert Love) | How the actual Linux kernel works | [→](https://www.rlove.org/) |
| LWN.net — kernel articles | Current kernel development, in-depth | [→](https://lwn.net/) |
| The Linux Programming Interface (Kerrisk) | Comprehensive Linux/UNIX systems programming | [→](https://man7.org/tlpi/) |
| Linux source code (bootlin cross-reference) | Browse the actual kernel source | [→](https://elixir.bootlin.com/linux/latest/source) |

</details>

---

<details>
<summary><strong>📺 Layer 3 — Big Series</strong></summary>

- [core dumped](https://www.youtube.com/@CoreDumped) — Linux internals, ELF format, memory — meticulous, in-depth
- [Linus Torvalds: Linux history (TED)](https://www.youtube.com/watch?v=o8NPllzkFhE) — context, not technical
- [MIT 6.S081 full semester](https://www.youtube.com/playlist?list=PLTsf9UeqkReZHXWY9yJvTwLJWYYPcKEqK) — 26 lectures

</details>

---

## Done when...

You can explain: what happens between `./myprogram` and `main()` executing, what a page fault is, how `fork()` and `exec()` work together, and why your Arch system has `/proc/` and what's in it.
