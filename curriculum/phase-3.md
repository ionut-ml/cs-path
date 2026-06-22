---
title: Phase 3 — Systems Programming in C
parent: Curriculum
nav_order: 7
---

# Phase 3 — Systems Programming in C

## Why C?

C is the language that unlocks everything else:
OS internals, networking, compilers, databases, and even ML (see llm.c).
Beej's guide is free, phone-readable, and written for adults.

---

<details open markdown="1">
<summary><strong>🎯 Layer 0 — Must Do</strong></summary>

## 📱 Phone Reading

| Resource | Why | Link |
|----------|-----|------|
| Beej's Guide to C | Free, scrollable, best C intro for adults | [→](https://beej.us/guide/bgc/html/split/index.html) |
| Memory Allocators 101 | Write a simple malloc — great phone read | [→](https://arjunsreedharan.org/post/148675821737/memory-allocators-101-write-a-simple-memory) |

## 🏗 Weekend Project — Build kilo (text editor in C)

~1000 lines of C. Build a working text editor in your terminal.
Teaches: file I/O, terminal control, data structures, memory management.
**Do this as your first real C project.**

[→ viewsourcecode.org/snaptoken/kilo](https://viewsourcecode.org/snaptoken/kilo/)

## Reading Order

1. Beej's C Ch 1–9 (variables → pointers) — pair with: start kilo steps 1–50
2. Beej's C Ch 10–20 (structs, malloc, file I/O) — pair with: finish kilo
3. Memory Allocators 101 — after you understand malloc

**Done when Layer 0 complete:** You've built kilo, can write C that uses malloc/free without leaking, reads/writes files, and handles pointers without fear.

</details>

---

<details markdown="1">
<summary><strong>📖 Layer 1 — Go Deeper</strong></summary>

| Resource | Why | Link |
|----------|-----|------|
| CS:APP (CMU) | THE systems textbook — Ch 1–3 after kilo | [→](https://csapp.cs.cmu.edu/3e/home.html) |
| Low Level Programming University | Structured low-level roadmap | [→](https://github.com/gurugio/lowlevelprogramming-university) |
| lowlevel.academy | Curated low-level CS learning path | [→](https://lowlevel.academy/) |
| Jacob Sorber — C series | Methodical, calm C systems programming. Better for depth than entertainment. | [→](https://www.youtube.com/@JacobSorber) |
| dr Jonas Birch — Learn C from scratch | 9-hour meticulous build-along course | [→](https://www.youtube.com/watch?v=wzMaNVSqfYw) |
| dr Jonas Birch — Memory allocator in C | 2-hour deep dive on malloc internals | [→](https://www.youtube.com/watch?v=J1lMQKTwEX0) |

</details>

---

<details markdown="1">
<summary><strong>🔬 Layer 2 — Deep Dive</strong></summary>

| Resource | Why | Link |
|----------|-----|------|
| CS:APP Ch 5–6 | Memory hierarchy, code optimization | [→](https://csapp.cs.cmu.edu/3e/home.html) |
| Tsoding Daily — C projects | Live-coding in C, shows real thinking process | [→](https://www.youtube.com/@TsodingDaily) |
| dr Jonas Birch — DB server in C | 10-hour build of a database server | [→](https://www.youtube.com/watch?v=1pMU6P8CuxU) |
| dr Jonas Birch — Network programming in C | 9-hour project-based networking in C | [→](https://www.youtube.com/watch?v=14YO3xjm6LY) |

</details>

---

<details markdown="1">
<summary><strong>📺 Layer 3 — Big Series</strong></summary>

- [Molly Rocket / Casey Muratori — Performance-Aware Programming](https://www.youtube.com/@MollyRocket) — meticulous, hardware-aware C. Use as reference once you know the basics.
- [Handmade Hero archive](https://hero.handmade.network/episode/code) — 800+ episodes of building a game from scratch in C. **Search within it** — don't start from episode 1.
- [Low Level Learning](https://www.youtube.com/@LowLevelLearning) — shorter videos, good for specific topics

</details>

---

## Done when...

You can write a C program that: uses malloc/free without leaking, reads/writes files, handles pointers without fear.

