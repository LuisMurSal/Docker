# Guía de Docker e Instalación de Aplicaciones

## ¿Qué es Docker?

Docker es una plataforma que permite crear, desplegar y ejecutar aplicaciones en contenedores. Un contenedor es una unidad estandarizada de software que empaqueta el código y todas sus dependencias para que la aplicación se ejecute de manera rápida y confiable en diferentes entornos. 

### Ventajas de Docker:
- Portabilidad: Los contenedores funcionan de la misma manera sin importar dónde se ejecuten.
- Eficiencia: Utiliza menos recursos que las máquinas virtuales.
- Escalabilidad: Facilita la gestión de múltiples instancias de una aplicación.

---

## Instalación de Docker

1. **Actualizar repositorios del sistema:**
   ```bash
   sudo apt update && sudo apt upgrade -y
2. **Instalar dependencias:**
   ```bash
   sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
3. **Añadir la clave GPG de Docker:**
   ```bash
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
4. **Añadir el repositorio de Docker:**
   ```bash
   echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
5. **Instalar Docker:**
   ```bash
   sudo apt update && sudo apt install docker-ce docker-ce-cli containerd.io -y
6. **Verificar instalación:**
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
