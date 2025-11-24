# Entorno de Desarrollo para Plugins de WordPress

Este repositorio proporciona un entorno de desarrollo completo con Docker para crear y probar plugins de WordPress de manera local.

## 🚀 Características

- **WordPress**: Última versión
- **MySQL 8**: Base de datos
- **phpMyAdmin**: Interfaz web para gestión de base de datos
- Configuración simple y estandarizada
- Carpeta dedicada para desarrollo de plugins

## 📋 Requisitos Previos

- Docker
- Docker Compose

## ⚙️ Configuración Inicial

1. **Clonar el repositorio**
   ```bash
   git clone https://github.com/rubiohernanmatias/no-programas-solo.git
   cd no-programas-solo
   ```

2. **Crear el archivo de variables de entorno**
   ```bash
   cp .env.example .env
   ```
   
   Por defecto, todas las credenciales están configuradas como `wp` para simplificar el desarrollo.

3. **Crear la carpeta de plugins**
   ```bash
   mkdir -p plugins-demo
   ```

4. **Iniciar los contenedores**
   ```bash
   docker-compose up -d
   ```

## 🌐 Acceso a los Servicios

- **WordPress**: http://localhost:8080
- **phpMyAdmin**: http://localhost:8081

### Credenciales por Defecto

- **Base de datos**: `wp`
- **Usuario**: `wp`
- **Contraseña**: `wp`

## 📁 Estructura del Proyecto

```
.
├── docker-compose.yml    # Configuración de Docker
├── .env.example          # Template de variables de entorno
├── .gitignore           # Archivos ignorados por Git
├── plugins-demo/        # Carpeta para tus plugins (montada en WP)
└── README.md            # Este archivo
```

## 🔧 Desarrollo de Plugins

Los plugins que crees o instales en la carpeta `plugins-demo/` aparecerán automáticamente en WordPress bajo:
- **Ruta WordPress**: `/wp-content/plugins/`
- **Ruta Local**: `./plugins-demo/`

### Crear un Plugin Nuevo

1. Crear una carpeta dentro de `plugins-demo/`:
   ```bash
   mkdir plugins-demo/mi-plugin
   ```

2. Crear el archivo principal del plugin:
   ```bash
   touch plugins-demo/mi-plugin/mi-plugin.php
   ```

3. Activar el plugin desde el panel de WordPress (http://localhost:8080/wp-admin)

## 🛠️ Comandos Útiles

```bash
# Iniciar los contenedores
docker-compose up -d

# Detener los contenedores
docker-compose down

# Ver logs
docker-compose logs -f

# Reiniciar servicios
docker-compose restart

# Eliminar todo (incluye volúmenes)
docker-compose down -v
```

## 📝 Notas

- Los datos de WordPress y MySQL se almacenan en volúmenes de Docker para persistir entre reinicios
- La carpeta `plugins-demo/` está en `.gitignore` para evitar subir plugins de terceros, pero puedes modificarlo según tus necesidades
- Este entorno está optimizado para desarrollo, **no para producción**

## 🤝 Contribuir

Si encuentras algún problema o tienes sugerencias, no dudes en abrir un issue o pull request.

## 📄 Licencia

Este proyecto es de código abierto y está disponible bajo la licencia MIT.
