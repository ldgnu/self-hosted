## ✍️ Ghost Blog – Self-hosted en Docker

Este stack te permite levantar tu propio blog personal usando [Ghost](https://ghost.org/), un CMS moderno y minimalista, completamente self-hosted, con soporte para publicaciones, membresías y más.

---

### 🧱 Stack Tecnológico

- **Ghost**: CMS rápido y liviano para blogging.
- **MySQL**: Base de datos persistente para Ghost.
- **Docker Compose**: Orquestación de servicios.
- **.env file**: Gestión de variables sensibles fuera del código.

---

### 🚀 ¿Cómo levantar el servicio?

1. **Cloná el repo o copiá esta carpeta**:

```bash
git clone https://github.com/ldgnu/self-hosted.git
cd self-hosted/ghost
```

2. **Editá el archivo `.env` con tus datos**:

```env
GHOST_URL=http://blog.tudominio.com
MYSQL_DATABASE=ghost
MYSQL_USER=ghost_user
MYSQL_PASSWORD=unaPassMuySegura123
```

3. **Levantá todo con Docker Compose**:

```bash
docker-compose up -d
```

4. **Accedé a tu blog en**:  
👉 `http://localhost:2368` (o la URL que pusiste en `.env`)

---

### 📁 Estructura

```bash
ghost/
├── docker-compose.yml
├── .env
├── content/              # Contenido persistente del blog
└── mysql/                # Volumen de la base de datos
```

---

### 🔐 Buenas prácticas de seguridad

- ✅ **No guardes contraseñas en el YAML**: usá `.env` como hicimos.
- 🔐 **Cambiá el usuario root** por un user dedicado (`ghost_user`).
- 🔄 **Backup** regular del volumen de `ghost/mysql`.
- 🔍 **Protegé tu instancia con un proxy inverso** (NGINX o Traefik con HTTPS).
- 📦 Usá `cap_add` y `security_opt` para agregar protección extra (ya configurado).

---

### 💡 Tips útiles

- Usá [Admin de Ghost](https://ghost.org/docs/) para importar/exportar contenido.
- Montá tu dominio con Cloudflare + Traefik/NGINX y sacale un Let's Encrypt.
- Conectalo a un CDN para servir imágenes más rápido.
- Hacé backup con herramientas como **Duplicati** o **Restic**.

