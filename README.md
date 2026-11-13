# template-2026 WordPress

## English Instructions

## Requirements
- Docker
- Docker Compose

## Docker Container Name (docker-compose.yaml)

Make sure the `container_name` used for phpMyAdmin and Node.js is unique for each project.

Example:

```yaml
phpmyadmin:
    image: phpmyadmin/phpmyadmin
    restart: always
    container_name: phpmyadmintemplate2026
    depends_on:
        - db

node:
    image: node:22-bookworm
    container_name: nodetemplate2026
```

## Starting the Project

To start the WordPress development environment, run the following command from the project root directory:

```bash
docker compose up
```

Docker Compose automatically starts the following services:

- **MySQL 8.0:** Database server.
- **WordPress:** WordPress running with PHP 8.3 and Apache.
- **phpMyAdmin:** Database administration interface.
- **Node.js 22:** Automatically manages Yarn dependencies and watches for file changes.

For an existing project, you can import your own database using phpMyAdmin. When starting a new project, use the WordPress installation assistant to configure the database.

You can access phpMyAdmin at:

```text
http://localhost:8081/
```

To access the WordPress website, use:

```text
http://localhost:8000
```

## Node.js + Yarn (Docker)

Node.js and Yarn are managed automatically through the Docker Compose `node` service.

When starting the containers, Docker automatically executes:

```bash
corepack enable && yarn install && yarn watch
```

This process installs the project dependencies and starts watching for changes in the theme files.

There is no need to install Node.js or Yarn locally or execute these commands manually.

The `node_modules` directory is managed through a Docker volume, keeping dependencies isolated from the local environment and persistent between container restarts.

Enjoy editing :)

---

# Instrucciones en Español

## Requisitos
- Docker
- Docker Compose

## Nombre de los contenedores Docker (docker-compose.yaml)

Asegúrate de que el `container_name` utilizado para phpMyAdmin y Node.js sea único para cada proyecto.

Ejemplo:

```yaml
phpmyadmin:
    image: phpmyadmin/phpmyadmin
    restart: always
    container_name: phpmyadmintemplate2026
    depends_on:
        - db

node:
    image: node:22-bookworm
    container_name: nodetemplate2026
```

## Iniciar el proyecto

Para iniciar el entorno de desarrollo de WordPress, ejecuta el siguiente comando desde la raíz del proyecto:

```bash
docker compose up
```

Docker Compose inicia automáticamente los siguientes servicios:

- **MySQL 8.0:** Servidor de base de datos.
- **WordPress:** WordPress con PHP 8.3 y Apache.
- **phpMyAdmin:** Interfaz para administrar la base de datos.
- **Node.js 22:** Administra automáticamente las dependencias de Yarn y observa los cambios en los archivos.

Para un proyecto existente, puedes importar tu propia base de datos utilizando phpMyAdmin. Si estás iniciando un proyecto nuevo, utiliza el asistente de instalación de WordPress para configurar la base de datos.

Puedes acceder a phpMyAdmin desde la URL:

```text
http://localhost:8081/
```

Para ingresar al sitio web utiliza la URL:

```text
http://localhost:8000
```

## Node.js + Yarn (Docker)

Node.js y Yarn se administran automáticamente mediante el servicio `node` de Docker Compose.

Al iniciar los contenedores, Docker ejecuta automáticamente:

```bash
corepack enable && yarn install && yarn watch
```

Este proceso instala las dependencias del proyecto y comienza a observar los cambios realizados en los archivos del tema.

No es necesario instalar Node.js ni Yarn en el equipo local, ni ejecutar estos comandos manualmente.

El directorio `node_modules` se administra mediante un volumen de Docker, manteniendo las dependencias aisladas del entorno local y conservándolas entre reinicios de los contenedores.

¡Disfruta editando! :)
