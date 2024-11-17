# Guía de Docker e Instalación de Aplicaciones en Fedora

## ¿Qué es Docker?

Docker es una plataforma que permite crear, desplegar y ejecutar aplicaciones en contenedores. Un contenedor es una unidad estandarizada de software que empaqueta el código y todas sus dependencias para que la aplicación se ejecute de manera rápida y confiable en diferentes entornos. 

### Ventajas de Docker:
- Portabilidad: Los contenedores funcionan de la misma manera sin importar dónde se ejecuten.
- Eficiencia: Utiliza menos recursos que las máquinas virtuales.
- Escalabilidad: Facilita la gestión de múltiples instancias de una aplicación.

---

## Instalación de Docker en Fedora

1. **Actualizar repositorios del sistema:**
   ```bash
   sudo dnf update -y
2. **Instalar dependencias:**
   ```bash
   sudo dnf install dnf-plugins-core -y
3. **Añadir el repositorio de Docker:**
   ```bash
   sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo
4. **Instalar Docker:**
   ```bash
   sudo dnf install docker-ce docker-ce-cli containerd.io -y
5. **Iniciar y habilitar el servicio de Docker**
   ```bash
   sudo systemctl start docker
   sudo systemctl enable docker
6. **Iniciar y habilitar el servicio de Docker**
   ```bash
   docker --version

## Aplicaciones para instalar con Docker

## 1. CodeLink

   CodeLink es una herramienta para gestionar y visualizar código colaborativamente.
   
1. Crear y ejecutar el contenedor:
   ```bash
   docker run -d --name codelink -p 8080:80 codelink/codelink:latest
2. Acceder desde el navegador: http://localhost:8080

## 2. Kanboard

   Kanboard es una herramienta de gestión de proyectos basada en tableros Kanban.
   
1. Crear y ejecutar el contenedor:
   ```bash
   docker run -d --name kanboard -p 8081:80 kanboard/kanboard:latest
2. Acceder desde el navegador: http://localhost:8081

## 3. Excalidraw

   Excalidraw es una aplicación de dibujo colaborativo para diagramas y bocetos.
   
1. Crear y ejecutar el contenedor:
   ```bash
   docker run -d --name excalidraw -p 8082:5000 excalidraw/excalidraw:latest
2. Acceder desde el navegador: http://localhost:8082

## Notas al crear los contenedores

-Asegúrate de que los puertos (8080, 8081, 8082) estén libres antes de iniciar los contenedores.
-Puedes usar otros puertos, estan a tu disposición mientras esten libres


