---
title: Phase 7 — Networking
parent: Curriculum
nav_order: 11
---

# Phase 7 — Networking

## Approach

Beej's Network Programming is your phone textbook — one chapter per session.
After reading, build the HTTP server to apply what you learned.

---

<details open markdown="1">
<summary><strong>🎯 Layer 0 — Must Do</strong></summary>

## 📱 Phone Reading

| Resource | Why | Link |
|----------|-----|------|
| Beej's Guide to Network Programming | The gold standard. Free, scrollable. | [→](https://beej.us/guide/bgnet/) |
| RFC 1180 (TCP/IP Tutorial) | Foundational RFC, short and surprisingly readable | [→](https://datatracker.ietf.org/doc/html/rfc1180) |

## 🏗 Project — HTTP server from scratch

Parse requests, serve files, handle connections. No framework — raw sockets in C.

**Done when Layer 0 complete:** You can write a TCP server in C that accepts connections, reads HTTP requests, and sends responses.

</details>

---

<details markdown="1">
<summary><strong>📖 Layer 1 — Go Deeper</strong></summary>

| Resource | Why | Link |
|----------|-----|------|
| Computer Networking: A Top-Down Approach (Kurose & Ross) | Best theory companion to Beej; free PDF | [→](https://github.com/TimorYang/Computer-Networking-Keith-Ross/blob/main/book/Kurose%2C%20James%20F._Ross%2C%20Keith%20W%20-%20Computer%20networking_%20a%20top-down%20approach-Pearson%20%282017%29.pdf) |

## 🎥 Key Videos

- [Hussein Nasser — Networking fundamentals playlist](https://www.youtube.com/@hnasr/playlists)
- [ThePrimeagen — From TCP to HTTP](https://www.youtube.com/watch?v=FknTw9bJsXM) — makes protocols concrete by tracing them

## 🏗 More Projects

- **Redis clone (build-your-own.org)** — key-value store + networking + data structures [→](https://build-your-own.org/redis/)

</details>

---

<details markdown="1">
<summary><strong>🔬 Layer 2 — Deep Dive</strong></summary>

- **TCP/IP stack from scratch (level-ip)** — build the actual network stack [→](https://github.com/saminiir/level-ip)
- [Hussein Nasser — How HTTPS works](https://www.youtube.com/watch?v=j9QmMEWmcfo)
- [freeCodeCamp Computer Networking full course](https://www.youtube.com/watch?v=qiQR5rTSshw) — 8 hours, use as reference

</details>

---

## Done when...

You can write a TCP server in C that accepts connections, reads HTTP requests, and sends responses.

