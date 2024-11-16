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
