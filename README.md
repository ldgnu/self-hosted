# 🧠 Un poco de Mi infra – Self-hosted 🚀

¡Bienvenidx a mi repositorio de configuraciones y servicios self-hosted!

Este repo es mi backup técnico y mental: acá guardo todo lo que uso, configuro y tuneo en mis servidores, tanto en VPS como en mi homelab.  
Objetivo: reemplazar **todos** los servicios online posibles por soluciones **100% self-hosted**.

---

## 🧰 Tech Stack & Filosofía 🧠

- 🐧 Linux (Arch + Debian/Ubuntu según el caso)
- 🐳 Docker & Docker Compose
- 🧵 Traefik + Nginx para proxying
- 🛢 PostgreSQL / MySQL / SQLite
- 🔐 2FA con Bitwarden (por ahora)
- 🧠 Ansible para automatizar la provisión (WIP)
- 🔍 Logs, monitoreo y backups
- 📁 Git para control de versiones
- 📜 Filosofía: **Self-host todo lo que se pueda**, manteniendo privacidad, control y diversión

---

## 🔁 Servicios que estoy reemplazando

| Servicio Comercial | Alternativa Self-hosted    | Proyecto             |
|--------------------|-----------------------------|----------------------|
| Google Drive       | Nextcloud + WebDAV          | `nextcloud/`         |
| Google Photos      | Immich o Photoprism (WIP)   |                      |
| Gmail              | Mailu o Mailcow (WIP)       |                      |
| Google Keep        | Joplin + Trilium            | `joplin/`, `trilium-data/` |
| Google Docs        | Cryptpad / Collabora / OnlyOffice | `docmost/`         |
| YouTube            | PeerTube (WIP)              |                      |
| Spotify            | Navidrome (WIP)             |                      |
| WhatsApp/Telegram  | Matrix + Element            | `matrix/`, `element/`|
| Dropbox            | Nextcloud + Duplicati       | `nextcloud/`, `duplicati/` |
| Netflix/Plex       | Jellyfin                    | `jellyfin/`          |

---

## 📁 Estructura del Repo (Work In Progress)

```bash
.
├── README.md                  # Este archivo
├── index.html                 # Landing local
├── docker/                    # Compose files separados por servicio
├── ansible/                   # Playbooks para provisión (en desarrollo)
├── configs/                   # Configs generales (nginx, fail2ban, ssh, etc.)
├── scripts/                   # Scripts útiles varios
└── [carpetas de servicios]    # Cada servicio tiene su carpeta individual
```

---

## 🧩 Servicios Self-hosted del Repo

- 🔧 **Infra & Gestión**
  - Portainer, Watchtower, Uptime-Kuma, Homer, Dashy, Glance
- 🔐 **Auth & Seguridad**
  - Authelia / Authentik, Wireguard, CrowdSec, Fail2ban
- ☁️ **Cloud & Backup**
  - Nextcloud, Duplicati, Rclone, Borg (WIP), Cloudflare Proxy
- 🖼 **Media & Docs**
  - Jellyfin, Trilium, Paperless-ngx, Stirling-PDF, Wallabag
- 📬 **Mensajería & Comms**
  - Matrix + Element, Gotify, Apprise
- 🧠 **Productividad & Tools**
  - Excalidraw, Puter, EmulatorJS, Notemark, Joplin
- 🖥 **Web & Dev**
  - Gitea, Nginx Proxy, Traefik, SearXNG, Whoogle, Ghost
- 🧪 **Testing & Nerd Corner**
  - kasm, webtop (Kali, Ubuntu Mate, Arch+i3), QEMU, VNC, etc.

---

## 📌 Objetivos del Proyecto

- [x] Centralizar todo en un solo repo versionado
- [x] Organizar por carpetas separadas y modulares
- [ ] Agregar documentación por servicio
- [ ] Playbooks con Ansible para deploy rápido
- [ ] Reemplazar TODO lo que dependa de BigTech
- [ ] Documentar el proceso de migración

---

## ❤️ Créditos y agradecimientos

Este proyecto es un mashup de muchas ideas, tutoriales y locuras de la comunidad tech y del mundo self-hosted.  
Inspirado por [awesome-selfhosted](https://github.com/awesome-selfhosted/awesome-selfhosted) y el laburo de miles de flacos que comparten todo lo que hacen. 🙌

---

> **Mantenete libre, curioso y con el control de tus datos. Viva el self-hosting .** 🔥

```
