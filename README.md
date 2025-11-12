# 🖥️ Webtop — Entorno de Escritorio Linux en el Navegador

Implementación de **Webtop** (Ubuntu MATE) con Docker Compose.  
Webtop permite ejecutar un entorno de escritorio completo (Ubuntu, Alpine, Fedora o Arch) accesible desde cualquier navegador web moderno.

---

## ✨ Características

- **Entorno de escritorio completo** accesible vía navegador.
- **Distribuciones soportadas:** Alpine, Ubuntu, Fedora y Arch.
- **Soporte multiusuario y persistente.**
- **Integración con Docker** para administración avanzada.
- **Compatibilidad internacional** (idioma y localización configurables).

---

## ⚙️ Estructura del Proyecto

```bash
webtop/
├── docker-compose.yml
├── config/             # Configuración persistente del contenedor
└── /var/run/docker.sock # (Opcional) Integración con Docker
```

---

## 🚀 Despliegue

1. **Clona el repositorio:**
   ```bash
   git clone https://github.com/JLalib/webtop-docker.git
   cd webtop-docker
   ```

2. **Revisa y personaliza las variables en el archivo `docker-compose.yml`:**
   ```yaml
   environment:
     - PUID=1000
     - PGID=1000
     - TZ=Europe/Madrid
     - CUSTOM_USER=admin
     - PASSWORD=p4ssw0rd
     - LC_ALL=es_ES.UTF-8
   ```

3. **Inicia el contenedor:**
   ```bash
   docker compose up -d
   ```

4. **Accede desde el navegador:**
   - URL principal: [http://localhost:3000](http://localhost:3000)
   - Usuario: `admin`
   - Contraseña: `p4ssw0rd`

---

## 🔧 Puertos Expuestos

| Puerto | Descripción |
|---------|--------------|
| 3000 | Interfaz principal de escritorio web |
| 3001 | Puerto alternativo o VNC si está habilitado |

---

## 🔐 Seguridad

- **Cambia inmediatamente la contraseña** por una más segura antes de exponer el servicio a Internet.
- Configura HTTPS mediante un proxy inverso (ej. Nginx, Traefik).
- Limita el acceso al puerto 3000 si solo se usará en red local.

---

## 🧠 Recursos

- [Repositorio oficial](https://github.com/linuxserver/docker-webtop)  
- [Documentación LinuxServer.io](https://docs.linuxserver.io/images/docker-webtop)  
- [Webtop en Docker Hub](https://hub.docker.com/r/linuxserver/webtop)

---

📦 **Distribución en uso:** `ubuntu-mate`  
Para cambiar de sabor, sustituye la imagen por una de las siguientes:
- `lscr.io/linuxserver/webtop:alpine-kde`
- `lscr.io/linuxserver/webtop:fedora-xfce`
- `lscr.io/linuxserver/webtop:arch-mate`
