
### ✅ `docker-compose.yml` limpio con variables

```yaml
version: '3.1'
services:

  ghost-server:
    image: ghost:latest
    cap_add:
      - CAP_SYS_NICE
    security_opt:
      - seccomp:unconfined
    restart: always
    ports:
      - "2368"
    depends_on:
      - ghost-db
    environment:
      url: ${GHOST_URL}
      database__client: mysql
      database__connection__host: ghost-db
      database__connection__user: ${MYSQL_USER}
      database__connection__password: ${MYSQL_PASSWORD}
      database__connection__database: ${MYSQL_DATABASE}
    volumes:
      - ./ghost/content:/var/lib/ghost/content

  ghost-db:
    image: mysql:8
    security_opt:
      - seccomp:unconfined
    restart: always
    command: --default-authentication-plugin=mysql_native_password
    environment:
      MYSQL_ROOT_PASSWORD: ${MYSQL_PASSWORD}
      MYSQL_DATABASE: ${MYSQL_DATABASE}
      MYSQL_USER: ${MYSQL_USER}
      MYSQL_PASSWORD: ${MYSQL_PASSWORD}
    volumes:
      - ./ghost/mysql:/var/lib/mysql
```

---

### ✅ `.env` (para poner en la raíz del proyecto)

```dotenv
# Ghost blog
GHOST_URL=http://blog.tudominio.com.ar

# MySQL config
MYSQL_DATABASE=ghost
MYSQL_USER=root
MYSQL_PASSWORD=unaPassSegura123
```

> ⚠️ Consejo J usá algo mejor que `root` como usuario si podés, por ejemplo `ghost_user`, y hacé que Ghost tenga solo acceso a su base, sin superpoderes.

