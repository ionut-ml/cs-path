---
title: Weekend Projects
parent: Plans
nav_order: 2
---

# 🏗 Weekend Projects

> **Rule:** Finish one project before starting the next.  
> Projects teach more at 80–100% than 5 projects at 20%.

---

## Tier 1 — Must Build

These are the projects that change how you think. Do them in order.

### Project 1: Nand2Tetris Part 1

**Build a full computer from NAND gates.**

| | |
|---|---|
| **Why** | Best "how does it all work" experience in CS self-study |
| **Time** | 6–8 weekends |
| **Link** | [nand2tetris.org/course](https://www.nand2tetris.org/course) |
| **Pair with** | Phone Queue A |

| Chapter | Topic | Weekends |
|---------|-------|---------|
| 1 | Boolean Logic | 1 |
| 2 | Boolean Arithmetic | 1 |
| 3 | Sequential Logic | 1 |
| 4 | Machine Language | 1 |
| 5 | Computer Architecture | 1–2 |
| 6 | Assembler | 1–2 |

---

### Project 2: kilo — Text Editor in C

**~1000 lines of C. Build a working terminal text editor.**

| | |
|---|---|
| **Why** | Your first real C project. Teaches file I/O, terminal, data structures. |
| **Time** | 3–4 weekends |
| **Link** | [viewsourcecode.org/snaptoken/kilo](https://viewsourcecode.org/snaptoken/kilo/) |
| **Pair with** | Phone Queue B (Beej's C Ch 1–10 first) |

---

### Project 3: SQLite from Scratch

**Follow cstack's tutorial to build a database in C.**

| | |
|---|---|
| **Why** | You're a DE — B-trees and paging at this level is a superpower |
| **Time** | 4–5 weekends |
| **Link** | [cstack.github.io/db_tutorial](https://cstack.github.io/db_tutorial/) |
| **Pair with** | Phone Queue E |
| **Do after** | Project 2 (you'll write cleaner C) |

---

### Project 4: Shell in C

**Build fork/exec/wait, pipes, redirects — the OS in miniature.**

| | |
|---|---|
| **Why** | Teaches UNIX fundamentals you use as a DE daily |
| **Time** | 2–3 weekends |
| **Link** | [codecrafters shell](https://github.com/codecrafters-io/build-your-own-x#build-your-own-shell) |

---

## Tier 2 — Highly Recommended

### Project 5: Write a Lisp Interpreter

Start in Python (50 lines), then rebuild in C.

| Step | Link | Time |
|------|------|------|
| Python version | [norvig.com/lispy.html](https://norvig.com/lispy.html) | 1 weekend |
| C version | [buildyourownlisp.com](https://buildyourownlisp.com/contents) | 2 weekends |

---

### Project 6: HTTP Server from Scratch

Parse HTTP, serve files, handle concurrent connections.

- Build using Beej's Network Programming as reference
- Or use CodeCrafters: [app.codecrafters.io/courses/http-server](https://app.codecrafters.io/courses/http-server)
- **2–3 weekends**

---

### Project 7: Redis Clone (CodeCrafters)

Key-value store + networking + data structures. Directly relevant to DE.

- [app.codecrafters.io/courses/redis](https://app.codecrafters.io/courses/redis)
- **2–3 weekends**

---

### Project 8: Ray Tracer

CPU-based ray tracer — linear algebra applied in code.

- [raytracing.github.io](https://raytracing.github.io/books/RayTracingInOneWeekend.html)
- **3–4 weekends**

---

## Tier 3 — When You're Ready

| Project | Topic | Link |
|---------|-------|------|
| Write Yourself a Git | Version control internals | [wyag.thb.lt](https://wyag.thb.lt/) |
| Write a compiler (acwj) | PLT + backend | [github DoctorWkt/acwj](https://github.com/DoctorWkt/acwj) |
| TCP/IP stack (level-ip) | Networking deep dive | [github saminiir/level-ip](https://github.com/saminiir/level-ip) |
| llm.c (Karpathy) | Synthesis: systems + ML | [github karpathy/llm.c](https://github.com/karpathy/llm.c) |
| Nand2Tetris Part 2 | OS + compiler | [nand2tetris.org](https://www.nand2tetris.org/course) |
| OpenSecurityTraining2 | Full RE curriculum | [p.ost2.fyi](https://p.ost2.fyi/) |

---

## 3-Month Sprint Plan

```
Month 1 (Weekends 1–8):
  Weeks 1–2: nand2tetris Ch 1–3
  Weeks 3–4: nand2tetris Ch 4–5
  Weeks 5–6: kilo text editor (finish it!)
  Weeks 7–8: nand2tetris Ch 6 (assembler)

Month 2 (Weekends 9–16):
  Weeks 1–2: Shell in C
  Weeks 3–4: Shell in C (pipes + builtins)
  Weeks 5–8: SQLite clone (Parts 1–6)

Month 3 (Weekends 17–24):
  Weeks 1–4: SQLite clone (Parts 7–13, B-tree)
  Weeks 5–8: HTTP server OR Redis clone
```
