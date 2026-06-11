# tarea-surge-parcial1

# 🚀 Práctica de DevOps: Pipeline CI/CD con Surge.sh y GitHub Actions

## 📖 Descripción del Proyecto
Este repositorio contiene la implementación práctica de un flujo básico de **Integración Continua (CI)** y **Despliegue Continuo (CD)**. El objetivo principal de esta tarea es automatizar la publicación de una página web estática sin intervención manual. 

Cada vez que se realiza un `push` o se integran nuevos cambios en la rama `main`, un flujo de trabajo (workflow) se dispara automáticamente en la nube, procesando el código y publicándolo directamente en un entorno en vivo.

## 🛠️ Tecnologías y Herramientas Utilizadas
* **HTML5 & CSS3:** Para la estructura y diseño de la página web estática.
* **Git & GitHub:** Para el control de versiones y alojamiento del código fuente.
* **GitHub Actions:** Como motor principal de automatización (Runner) para construir y ejecutar el pipeline.
* **Node.js & npm:** Utilizados en el contenedor virtual para instalar las dependencias necesarias de despliegue.
* **Surge.sh:** Plataforma de hosting en la nube (PaaS) encargada de alojar y servir la página web de forma rápida y segura.

## ⚙️ ¿Cómo funciona el Pipeline?
El archivo de configuración `.github/workflows/main.yaml` orquesta todo el proceso mediante los siguientes pasos automatizados:
1. **Trigger:** Detecta cualquier evento de tipo `push` en la rama principal (`main`).
2. **Checkout:** Clona el código fuente en un contenedor efímero de `ubuntu-latest`.
3. **Setup Node:** Configura el entorno de ejecución con la versión 20 de Node.js.
4. **Instalación:** Ejecuta `npm install -g surge` para preparar la herramienta de despliegue.
5. **Despliegue Seguro:** Se conecta a Surge utilizando un Token de autenticación inyectado de forma segura a través de **GitHub Secrets** (`SURGE_TOKEN`), garantizando que las credenciales nunca queden expuestas en el código público.

---
**Desarrollado por:** Sky Andujar  
**Materia:** Electiva 2 (DevOps)