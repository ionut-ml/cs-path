---
title: Rust
parent: Advanced Topics
nav_order: 3
---

# Advanced Topic — Rust

## Why Rust After C

After Phase 3 (Systems/C), Rust is the natural progression. It teaches the same concepts — ownership, lifetimes, memory layout — but the compiler enforces them. You can't write a use-after-free. You can't have a data race. The feedback loop is the compiler, not a segfault at 2am.

More concretely: the modern data engineering toolchain is increasingly Rust-native. **Polars** (DataFrame library), **DataFusion** (query engine), **DeltaRS** (Delta Lake), **Ballista** (distributed compute) — all written in Rust. You don't need to write Rust to use them, but knowing it lets you read the source, understand the performance characteristics, and contribute.

**Prerequisites:** Phase 3 (Systems/C) — ownership concepts will click immediately if you've wrestled with C memory manually.

---

<details open markdown="1">
<summary><strong>🎯 Layer 0 — Must Read</strong></summary>

| Resource | Why | Link |
|----------|-----|------|
| The Rust Book (official) | Free, online, canonical. The best language introduction written for any language. Phone-readable chapters. | [→](https://doc.rust-lang.org/book/) |
| Rustlings | Small exercises that force you to fix compiler errors — learns Rust syntax by doing | [→](https://github.com/rust-lang/rustlings) |

**Reading order:** Rust Book Ch 1–10 (ownership, structs, enums, error handling) → do Rustlings exercises for Ch 1–10 → continue book.

**Done when Layer 0 complete:** You understand ownership and borrowing, can explain why Rust doesn't have a garbage collector, and can write a small CLI tool.

</details>

---

<details markdown="1">
<summary><strong>📖 Layer 1 — Go Deeper</strong></summary>

| Resource | Why | Link |
|----------|-----|------|
| Rust by Example | Code-first companion to the book | [→](https://doc.rust-lang.org/rust-by-example/) |
| Comprehensive Rust (Google) | Free, modern, covers async | [→](https://google.github.io/comprehensive-rust/) |
| Polars user guide | Read how Polars uses Rust for lazy evaluation | [→](https://docs.pola.rs/) |

</details>

---

<details markdown="1">
<summary><strong>🔬 Layer 2 — Systems Programming in Rust</strong></summary>

| Resource | Why | Link |
|----------|-----|------|
| Programming Rust (O'Reilly) | Deep reference — available at some libraries | — |
| Async Rust (tokio book) | Async/await and the tokio runtime | [→](https://tokio.rs/tokio/tutorial) |
| Writing an OS in Rust (blog series) | The Rust equivalent of xv6 | [→](https://os.phil-opp.com/) |

</details>

---

## Done when...

You can write a CLI data processing tool in Rust, use Polars for a real data task, and read Polars source code and understand what's happening.
