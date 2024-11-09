# Guía de Uso de Docker

## ¿Qué es Docker?

Docker es una plataforma para desarrollar, enviar y ejecutar aplicaciones dentro de contenedores. Los contenedores son entornos ligeros, aislados y consistentes que permiten ejecutar aplicaciones de forma independiente, sin importar el sistema operativo subyacente.

Con Docker, puedes empaquetar tu aplicación junto con todas sus dependencias y ejecutarla de manera consistente en cualquier entorno. Esto hace que el despliegue y la gestión de aplicaciones sea más fácil y rápido.

---

## ¿Qué se puede hacer con Docker?

Docker ofrece una gran variedad de posibilidades que pueden ser útiles tanto en el desarrollo como en la producción. Aquí te presentamos algunos de los usos más comunes de Docker:

### 1. **Contenerización de Aplicaciones**
Docker permite encapsular aplicaciones y sus dependencias en contenedores, garantizando que se ejecuten de la misma manera en cualquier entorno (desarrollo, pruebas, producción). Esto elimina los problemas de "funciona en mi máquina".

**Ejemplo**: Una aplicación Node.js con sus dependencias se puede ejecutar en cualquier servidor que tenga Docker instalado, sin importar las diferencias en el sistema operativo o configuraciones locales.

### 2. **Desarrollo y Pruebas Aisladas**
Con Docker, puedes crear entornos de desarrollo aislados para cada proyecto. Esto es útil para evitar conflictos de dependencias entre proyectos.

**Ejemplo**: Puedes tener un contenedor para un proyecto de Node.js, otro para Python, y otro para una base de datos como PostgreSQL, todo ejecutándose en la misma máquina sin interferencias.

### 3. **Escalabilidad de Servicios**
Docker facilita la escalabilidad de aplicaciones al permitir la creación de múltiples instancias de un mismo contenedor. Esto es útil para aplicaciones que necesitan manejar un alto volumen de tráfico.

**Ejemplo**: Puedes usar Docker junto con herramientas como Docker Compose o Kubernetes para escalar tu aplicación de forma horizontal, añadiendo más contenedores según la demanda.

### 4. **Despliegue Continuo (CI/CD)**
Docker es ideal para implementar prácticas de integración continua y despliegue continuo (CI/CD). Puedes automatizar el proceso de construcción, prueba y despliegue de tu aplicación en un contenedor cada vez que se realicen cambios en el código.

**Ejemplo**: Configurar pipelines con herramientas como Jenkins, GitLab CI/CD o GitHub Actions que automáticamente construyen y despliegan contenedores Docker cuando hay nuevos commits en tu repositorio.

### 5. **Microservicios**
Docker es una excelente opción para arquitecturas de microservicios. Cada microservicio se puede ejecutar en su propio contenedor, facilitando su desarrollo, despliegue y mantenimiento de manera independiente.

**Ejemplo**: Si tienes una aplicación de comercio electrónico, podrías tener un contenedor para la autenticación, otro para el carrito de compras, otro para la base de datos, y más, todos funcionando de manera independiente pero comunicándose entre sí.

### 6. **Administración de Contenedores y Volúmenes**
Con Docker, puedes gestionar contenedores de manera eficiente utilizando comandos como `docker ps`, `docker stop`, `docker start`, `docker logs`, y muchos más. También puedes usar volúmenes para almacenar datos persistentes fuera del contenedor.

**Ejemplo**: Si tienes una base de datos dentro de un contenedor, puedes usar un volumen para almacenar los datos de manera que persistan incluso si el contenedor se reinicia o elimina.

### 7. **Entornos de Producción Aislados**
Docker permite desplegar aplicaciones en contenedores que están completamente aislados entre sí y del sistema operativo subyacente, lo que mejora la seguridad y la estabilidad de los entornos de producción.

**Ejemplo**: Puedes tener diferentes contenedores para servicios web, bases de datos y aplicaciones backend, todo corriendo de manera aislada en el mismo servidor físico o virtual.

### 8. **Compatibilidad con Cloud y Orquestadores**
Docker es compatible con plataformas de nube como AWS, Google Cloud, Azure, y con sistemas de orquestación como Kubernetes. Esto facilita el manejo de contenedores a gran escala en entornos de producción distribuidos.

**Ejemplo**: Puedes usar Kubernetes para gestionar el despliegue de varios contenedores Docker en una infraestructura distribuida, asegurando alta disponibilidad y escalabilidad automática.

---

## Comandos Básicos de Docker

A continuación, te dejo algunos comandos básicos de Docker para que puedas comenzar:

- **`docker --version`**: Muestra la versión de Docker instalada.
- **`docker pull <image>`**: Descarga una imagen desde Docker Hub.
- **`docker build -t <nombre_imagen> .`**: Construye una imagen Docker desde un `Dockerfile`.
- **`docker run <image>`**: Ejecuta un contenedor basado en una imagen.
- **`docker ps`**: Muestra los contenedores en ejecución.
- **`docker stop <container_id>`**: Detiene un contenedor en ejecución.
- **`docker start <container_id>`**: Inicia un contenedor detenido.
- **`docker exec -it <container_id> bash`**: Accede a un contenedor en ejecución mediante un shell interactivo.
- **`docker logs <container_id>`**: Muestra los logs de un contenedor.

---

## Ejemplo de Uso de Docker con un Proyecto Node.js

1. **Crea un archivo `Dockerfile`** en el directorio de tu proyecto:

   ```Dockerfile
   FROM node:14

   WORKDIR /usr/src/app

   COPY package*.json ./

   RUN npm install

   COPY . .

   EXPOSE 8080

   CMD ["node", "app.js"]
