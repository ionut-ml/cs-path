---
title: Phase 1 — UNIX & Arch Linux
parent: Curriculum
nav_order: 5
---

# Phase 1 — UNIX & Arch Linux

## Why This Is Phase 1

You use Arch Linux every day. Every phase that follows uses these tools. Learn them first, once, properly — then they're invisible infrastructure for all the work ahead.

---

<details open markdown="1">
<summary><strong>🎯 Layer 0 — Must Do</strong> &nbsp;(start here — minimum viable for every other phase)</summary>

## 📱 Phone Reading

| Resource | Why | Link |
|----------|-----|------|
| The Art of Command Line | 30 min read. Every item is immediately useful. | [→](https://github.com/jlevy/the-art-of-command-line) |
| Oh Shit, Git | Fix git mistakes in plain English. | [→](https://ohshitgit.com/) |
| Arch Wiki: Pacman | The definitive pacman reference. | [→](https://wiki.archlinux.org/title/Pacman) |
| Arch Wiki: Systemd | Everything about services, timers, journal. | [→](https://wiki.archlinux.org/title/Systemd) |

## 🏗 Project — Write Yourself a Git

Build a minimal `git` implementation in Python. Teaches object storage, hashing, branching internals.

[→ wyag.thb.lt](https://wyag.thb.lt/) — ~2 weekends

## Quick Wins (do these now)

- Install and configure `fzf` — fuzzy finder that changes how you navigate [→](https://github.com/junegunn/fzf)
- Install `ripgrep (rg)` — grep with sane defaults [→](https://github.com/BurntSushi/ripgrep)
- Set up tmux — persistent sessions, split panes [→](https://www.youtube.com/watch?v=DzNmUNvnB04)

**Done when Layer 0 is complete:** You can navigate, search, manage processes, and fix git mistakes entirely from the terminal without reaching for a GUI.

</details>

---

<details markdown="1">
<summary><strong>📖 Layer 1 — Go Deeper</strong> &nbsp;(shell scripting + system administration)</summary>

## Shell Scripting as a Language

| Resource | Why | Link |
|----------|-----|------|
| The Linux Command Line (Shotts) | Free book — shell scripting chapters (Part 4) | [→](https://linuxcommand.org/tlcl.php) |
| Advanced Bash-Scripting Guide | Reference, not linear reading — search when stuck | [→](https://tldp.org/LDP/abs/html/) |
| ShellCheck | Lints your shell scripts, teaches correct patterns | [→](https://www.shellcheck.net/) |

## Arch Linux System Administration

| Topic | Resource | Link |
|-------|----------|------|
| AUR + makepkg | Arch Wiki: AUR | [→](https://wiki.archlinux.org/title/Arch_User_Repository) |
| Dotfiles management | Arch Wiki: Dotfiles | [→](https://wiki.archlinux.org/title/Dotfiles) |
| systemd timers (cron replacement) | Arch Wiki: Systemd/Timers | [→](https://wiki.archlinux.org/title/Systemd/Timers) |
| journalctl fluency | `journalctl -f`, `-u service`, `--since "1 hour ago"` | Arch Wiki |
| Boot process | Arch Wiki: Arch boot process | [→](https://wiki.archlinux.org/title/Arch_boot_process) |

## Debugging Tools

| Tool | What it Does |
|------|-------------|
| `strace -p PID` | See every system call a process makes |
| `lsof -p PID` | What files/sockets a process has open |
| `ss -tuln` | Sockets in use (replacement for netstat) |
| `perf stat ./program` | CPU performance counters |
| `htop` / `btop` | Process tree with resource usage |

</details>

---

<details markdown="1">
<summary><strong>🔬 Layer 2 — Deep Dive</strong> &nbsp;(Linux internals)</summary>

| Resource | Why | Link |
|----------|-----|------|
| The Linux Programming Interface (Kerrisk) | The definitive Linux systems programming reference | [→](https://man7.org/tlpi/) |
| Linux From Scratch | Build a complete Linux system from source | [→](https://www.linuxfromscratch.org/) |
| Arch Wiki: Kernel | Compiling and configuring your own kernel | [→](https://wiki.archlinux.org/title/Kernel) |
| `procfs` / `sysfs` exploration | `cat /proc/PID/maps`, `/proc/PID/fd/`, `/sys/` — read the running system | — |

</details>

---

<details markdown="1">
<summary><strong>📺 Layer 3 — Big Series</strong> &nbsp;(return to when you want depth, not linearly)</summary>

- [Luke Smith — Arch Linux and UNIX philosophy](https://www.youtube.com/@LukeSmithxyz) — opinionated but technically sound
- [Chris Titus Tech — Linux configuration](https://www.youtube.com/@ChrisTitusTech) — practical Arch/Hyprland setups
- [DistroTube](https://www.youtube.com/@DistroTube) — deep UNIX tool usage

</details>

---

## Done when...

You write a shell script to automate something you do manually, it works without StackOverflow, and you understand what every line does.
