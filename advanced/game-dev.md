---
title: Game Development
parent: Advanced Topics
nav_order: 2
---

# Advanced Topic — Game Development

## Why Game Dev Belongs Here

Game development is applied CS at its most demanding: real-time systems, performance-critical code, memory management, linear algebra in practice, and physics simulation. The best educators in this space are working professionals who explain *why* things work, not just *how* to use an engine.

**Prerequisites:** Phase 3 (Systems/C) — you need to be comfortable writing C and thinking about memory.

---

<details open>
<summary><strong>🎯 Layer 0 — Must Watch</strong></summary>

| Resource | Why | Link |
|----------|-----|------|
| Casey Muratori — Performance-Aware Programming (2022) | Directly applicable to Phase 3 (C). How hardware-aware code actually works. Meticulous, no handwaving. | [→](https://www.youtube.com/@MollyRocket) |
| Jonathan Blow — Compiler development streams | Language design and systems thinking from a game dev perspective | [→](https://www.youtube.com/@jblow888) |

**On Handmade Hero:** Casey Muratori's full series (~800 episodes) of building a complete game from scratch in C is a reference library, not a course. **Do not start from episode 1 linearly.** Instead: search within it when you have a specific question (e.g., "how does Casey handle memory arenas" or "how does the game loop work"). It rewards targeted exploration.

</details>

---

<details>
<summary><strong>📖 Layer 1 — Structured Game Dev</strong></summary>

| Resource | Why | Link |
|----------|-----|------|
| Game Programming Patterns (free online) | Design patterns specific to game dev. Excellent, free, readable. | [→](https://gameprogrammingpatterns.com/contents.html) |
| Ray Tracing in One Weekend | Math + C — build a CPU ray tracer. Applies Phase 0 (linear algebra) directly. | [→](https://raytracing.github.io/books/RayTracingInOneWeekend.html) |
| Handmade Hero — targeted episodes | When you have a specific question, search the [episode guide](https://hero.handmade.network/episode/code) | — |

</details>

---

<details>
<summary><strong>🔬 Layer 2 — Graphics Programming</strong></summary>

| Resource | Why | Link |
|----------|-----|------|
| learnopengl.com | Free, comprehensive OpenGL tutorial | [→](https://learnopengl.com/) |
| Vulkan Tutorial | Modern graphics API — hard but rewarding | [→](https://vulkan-tutorial.com/) |
| 3Blue1Brown: Linear Algebra series | Visual intuition for the math you're using | [→](https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab) |

</details>

---

<details>
<summary><strong>📺 Layer 3 — Deep Reference Series</strong></summary>

- [Handmade Hero full archive](https://hero.handmade.network/episode/code) — 800+ episodes, treat as a searchable reference
- [Jonathan Blow — making Braid / The Witness talks](https://www.youtube.com/@jblow888) — game design + systems thinking
- [Casey Muratori — Clean Code, Horrible Performance](https://www.youtube.com/watch?v=tD5NrevFtbU) — also applies to Phase 9 SE practices

</details>

---

## Done when...

You've built a game loop that runs at a stable 60fps, understands why frame timing matters, and can render a moving object with a camera without using a game engine.
