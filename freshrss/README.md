```markdown
# 📰 FreshRSS - Self-Hosted RSS Reader

![FreshRSS Logo](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c7/Fresh-rss.svg/512px-Fresh-rss.svg.png)

FreshRSS es un lector RSS autoalojado liviano, rápido y con soporte multiusuario. Esta configuración te permite levantarlo en tu VPS o server local usando Docker en un toque.

---

## 🐳 Docker Compose

```yaml
version: '3'

services:
  freshrss:
    image: linuxserver/freshrss:latest
    container_name: freshrss
    restart: unless-stopped
    volumes:
      - ./config:/config
    ports:
      - 8989:80
```

---

## 📦 Volúmenes

- `./config:/config`: Guarda la configuración y base de datos de FreshRSS. Esto asegura que no pierdas nada si el contenedor se reinicia o lo recreás.

---

## 🚀 Cómo levantarlo

1. Cloná este repositorio:
   ```bash
   git clone https://github.com/ldgnu/self-hosted.git
   cd self-hosted
   ```

2. Levantá el servicio:
   ```bash
   docker compose up -d
   ```

3. Accedé desde tu navegador:
   ```
   http://localhost:8989
   ```

---

## 🛠️ Configuración inicial

Cuando ingreses por primera vez, seguí el asistente para:

- Crear tu usuario admin
- Elegir idioma
- Cargar tus primeros feeds RSS

---

## 🌐 Acceso desde otros contenedores

Para que otros contenedores puedan acceder a FreshRSS por hostname, podés:

1. Definir una red común en tus stacks de Docker.
2. Usar el hostname `freshrss` dentro de esa red.

---

## 🧠 Extras

- Panel de admin: `/i/`
- Importar OPML: desde la configuración
- Acceso multiusuario: activable en settings

---

## 🧼 Mantenimiento

- Ver logs:
  ```bash
  docker logs -f freshrss
  ```

- Backup:
  Guardá la carpeta `./config`

- Update:
  ```bash
  docker compose pull
  docker compose up -d
  ```

---

## ❤️ Créditos

Contenedor mantenido por [LinuxServer.io](https://docs.linuxserver.io/images/docker-freshrss)

---

```
