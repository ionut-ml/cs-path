---
title: Self-Hosting & Homelab
parent: Advanced Topics
nav_order: 4
---

# Advanced Topic — Self-Hosting & Homelab

## Why This Belongs Here

Running your own services teaches more about systems than reading about them. DNS, TLS, reverse proxies, containers, monitoring — abstract concepts become concrete when they're serving traffic to your phone.

**Prerequisites:** Phase 1 (UNIX/Arch) fully complete. You need to be comfortable with `systemd`, `journalctl`, and the command line before adding network services to the mix.

---

<details open>
<summary><strong>🎯 Layer 0 — First Services</strong></summary>

| Resource | Why | Link |
|----------|-----|------|
| How to Secure a Linux Server | Skim this before exposing anything to the internet | [→](https://github.com/imthenachoman/How-To-Secure-A-Linux-Server) |
| Arch Wiki: SSH | Key-based auth, `sshd_config` hardening | [→](https://wiki.archlinux.org/title/OpenSSH) |
| selfh.st — catalog of self-hostable apps | Browse what's worth running | [→](https://selfh.st/apps/) |

**Start with:** A Wireguard VPN (Arch Wiki) + a reverse proxy (Caddy or Nginx) + one service you actually use (Nextcloud, Vaultwarden, Immich, Gitea).

</details>

---

<details>
<summary><strong>📖 Layer 1 — Go Deeper</strong></summary>

| Topic | Resource | Link |
|-------|----------|------|
| Docker + Docker Compose | Containerize everything you self-host | [→](https://docs.docker.com/get-started/) |
| Caddy as reverse proxy | Automatic HTTPS, simple config | [→](https://caddyserver.com/docs/) |
| Monitoring with Grafana + Prometheus | Your first observability stack | [→](https://grafana.com/docs/grafana/latest/getting-started/) |
| Ansible for configuration management | Automate your server setup as code | [→](https://docs.ansible.com/ansible/latest/getting_started/) |

</details>

---

<details>
<summary><strong>🔬 Layer 2 — Kubernetes Path</strong></summary>

Run Kubernetes if you want to understand what your company's infrastructure does:

| Resource | Link |
|----------|------|
| k3s (lightweight Kubernetes) | [→](https://k3s.io/) |
| Kubernetes the Hard Way (Kelsey Hightower) | [→](https://github.com/kelseyhightower/kubernetes-the-hard-way) |

</details>

---

<details>
<summary><strong>📺 Layer 3 — Community</strong></summary>

- [r/selfhosted](https://www.reddit.com/r/selfhosted/) — what people are running and how
- [Wolfgang's Channel](https://www.youtube.com/@WolfgangsChannel) — practical homelab setups
- [Techno Tim](https://www.youtube.com/@TechnoTim) — homelab + Kubernetes + Ansible

</details>

---

## Done when...

You have at least one service running behind a reverse proxy with automatic HTTPS, deployed via Docker Compose, monitored with a dashboard, and you can restore it from a backup.
