# ☁️ Subir proyecto Docker a GitHub paso a paso

Esta guía documenta el proceso completo para versionar y subir tu proyecto (en este caso FreshRSS) a GitHub usando Git. Incluye los errores más comunes y cómo resolverlos.

---

## 🚀 Inicializar Git y primer commit

```bash
git init
git add .
git commit -m "Primer commit: Proyecto FreshRSS con Docker"
```

### 🧨 Problema:
> **Ups, agregué carpetas que no quería (ej: `config/`)**

### 💡 Solución:
1. Borrá todo del staging:
   ```bash
   git reset
   ```
2. Creá un archivo `.gitignore`:
   ```bash
   echo "config/" >> .gitignore
   ```
3. Volvé a agregar solo lo necesario:
   ```bash
   git add .
   git commit -m "Commit limpio sin carpetas innecesarias"
   ```

---

## 🐙 Crear repositorio en GitHub

1. Andá a https://github.com y creá un nuevo repositorio vacío (sin README, sin `.gitignore`).
2. Copiá la URL del repo (por ejemplo: `https://github.com/javisol/freshrss.git`)

---

## 🔗 Conectar repo local con GitHub

```bash
git remote add origin https://github.com/TU-USUARIO/freshrss.git
git branch -M main
git push -u origin main
```

### 🧨 Problema:
> `fatal: remote origin already exists.`

### 💡 Solución:
```bash
git remote remove origin
git remote add origin https://github.com/TU-USUARIO/freshrss.git
```

---

## 🔑 Autenticación con GitHub (SSH recomendado)

### ✅ Paso 1: Crear llave SSH (si no tenés una)

```bash
ssh-keygen -t ed25519 -C "tuemail@example.com"
```

Presioná enter varias veces. Te crea una clave en `~/.ssh/id_ed25519`.

### ✅ Paso 2: Copiar clave pública

```bash
cat ~/.ssh/id_ed25519.pub
```

Copiá todo el contenido.

### ✅ Paso 3: Agregarla en GitHub

- Entrá a [https://github.com/settings/keys](https://github.com/settings/keys)
- Click en **"New SSH key"**
- Pegá tu clave y guardá

### ✅ Paso 4: Usar SSH en tu repo

Cambiá el remote a usar SSH:

```bash
git remote set-url origin git@github.com:TU-USUARIO/freshrss.git
```

Probar conexión:

```bash
ssh -T git@github.com
```

Debería decir: `Hi TU-USUARIO! You've successfully authenticated.`

---

## 📤 Subir cambios al repo (día a día)

```bash
git add .
git commit -m "Cambios del día"
git push
```

---

## 🧼 Extra: .gitignore recomendado para proyectos Docker

```bash
# .gitignore
config/
.env
*.log
*.pid
*.swp
.DS_Store
```

---

## 🏁 Resultado Final

Tu proyecto ya está versionado, subido, documentado y listo para la gloria.

> Si querés ver tu README renderizado como Dios manda:  
> 📦 `https://github.com/TU-USUARIO/freshrss`

---

```

¿Querés que te lo prepare como archivo `.md` para descargar o lo vas a copiar directo en tu repo? También lo puedo meter en un README extendido si querés que sea parte del proyecto FreshRSS.
