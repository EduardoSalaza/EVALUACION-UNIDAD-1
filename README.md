# EVALUACION-UNIDAD-1

**Institución:** UNIVERSIDAD TECNOLOGICA AL NORTE DE GUANAJUATO  
**Carrera:** Ingeniería en Redes Inteligentes y Ciberseguridad  
**Grupo:** GIRI5081
**Unidad:** Unidad I – Entornos de desarrollo en la automatización de redes  
**Alumno:** Jesús Eduardo Salazar Venegas  
**Número de control:** 1221100896  
**Fecha:** 10 de junio de 2025  

---

##  Introducción

Este documento describe el procedimiento realizado para implementar un entorno de desarrollo enfocado en la automatización de redes, utilizando herramientas ampliamente adoptadas como Docker, Git y Visual Studio Code (VSCode). El objetivo principal fue instalar, configurar y verificar el correcto funcionamiento de dichas herramientas, necesarias para desplegar aplicaciones en contenedores.

Durante este proceso se aprendió cómo instalar Docker Engine y Docker Compose en Ubuntu, cómo trabajar con imágenes y contenedores, y cómo utilizar Git como sistema de control de versiones. Además, se presentan evidencias de verificación funcional mediante comandos como `docker run hello-world` y la ejecución de archivos `.yml`.

Este entorno es esencial en escenarios modernos de infraestructura digital donde la eficiencia, portabilidad y automatización son fundamentales. La experiencia adquirida también se complementó con recursos de la comunidad y documentación oficial. Todo el trabajo realizado se incluye en este repositorio, respetando el formato y los criterios solicitados.

---

##  Desarrollo

### 1. Herramientas utilizadas para automatización

####  Docker Engine
Permite crear y administrar contenedores que encapsulan aplicaciones con todas sus dependencias.

####  Docker Compose
Permite definir y correr múltiples contenedores con un solo archivo `.yml`, ideal para servicios que se comunican entre sí.

####  Docker Swagger (opcional)
Herramienta útil para documentar y probar APIs, no se utilizó directamente en esta unidad pero es parte del ecosistema.

---

### 2. Procedimiento de instalación

#### a) Visual Studio Code
```bash
sudo snap install code --classic
```

**INSTALACION DE GIT**
```bash
sudo apt update
sudo apt install git -y
git --version
```

**DOCKER ENGINE**
```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io -y
sudo usermod -aG docker $USER
newgrp docker
docker --version
```

**DOCKER COMPOSE**
```bash
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
docker run hello-world
```

**Evidencia de pruebas de verificación de funcionamiento**
```bash
docker run hello-world
```
**ARCHIVO DOCKER-COMPOSE.YML**
```bash
version: '3'
services:
  web:
    image: nginx
    ports:
      - "80:80"
```

**COMANDO DE EJECUCION**
```bash
docker-compose up -d
```

**Verificado en navegador: http://localhost muestra la página de Nginx.**

## Conclusión

Durante el desarrollo de esta actividad se logró configurar correctamente un entorno de desarrollo en Ubuntu para la automatización de redes. Se instalaron y configuraron herramientas clave como Git, VSCode y Docker. También se verificó el funcionamiento de Docker mediante la ejecución de contenedores simples.

Uno de los principales aprendizajes fue la comprensión del ciclo de vida de los contenedores y la importancia de los archivos .yml para definir múltiples servicios. Además, se mejoró la familiaridad con el uso de la terminal en Ubuntu y se fortalecieron conocimientos sobre la gestión de servicios desde Docker.

Este entorno será la base para futuros proyectos más complejos, como la orquestación de aplicaciones completas usando docker-compose, swarm, o incluso Kubernetes. La automatización de redes permite reducir tiempos de despliegue y errores manuales, lo cual es vital en la administración moderna de infraestructura digital.

## Bibliografía (Estilo APA 7)

Bell, P. (2020). Introducing GitHub: A Non-technical Guide. O'Reilly Media.
Gift, N., et al. (2019). Python for DevOps: Learn Ruthlessly Effective Automation. O'Reilly Media.
Hillar, G. C. (2016). Building RESTful Python Web Services. Packt Publishing.
Jackson, C., et al. (2020). Cisco Certified DevNet Associate DEVASC 200-901 Official Cert Guide. Cisco Press.
Tsitoara, M. (2019). Beginning Git and GitHub. Apress.
