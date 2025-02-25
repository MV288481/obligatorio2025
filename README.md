# Proyecto de Automatización con Ansible - Taller Febrero 2025
 
## Introducción
Este repositorio contiene el **Obligatorio del Taller de Servidores Linux Febrero 2025**, enfocado en la automatización de la configuración de servidores mediante **Ansible**.
 
El objetivo del proyecto es aplicar conocimientos básicos de **Ansible** sobre dos distribuciones Linux: **CentOS Stream 9** y **Ubuntu 24.04**, garantizando una implementación eficiente y segura.
 
## Características del Proyecto
Este desarrollo permite realizar diversas tareas clave, tales como:
 
 **Gestión de Equipos**: Configuración de `inventory.ini` con los grupos Ubuntu y CentOS.
 **Comandos Ad-Hoc**: Ejecución de acciones inmediatas como instalación de paquetes y monitoreo del sistema.
 **Implementación de Servidores Web**: Instalación de Apache y configuración de VirtualHost en sistemas CentOS.
 **Refuerzo de Seguridad**: Configuración de `ufw`, acceso SSH mediante claves y restricciones de autenticación en Ubuntu.
 **Uso de Handlers**: Aplicación de cambios solo cuando es requerido para optimizar recursos.
 
 
## Pasos para Iniciar
Para utilizar este repositorio y automatizar tareas, sigue estos pasos:
 
 **Descargar el repositorio**:
   ```sh
   git clone https://github.com/MV288481/obligatorio2025.git
   ```
 
 **Verificar que Ansible esté instalado** (Versión mínima recomendada: `2.14+`):
   ```sh
   ansible --version
   ```
 
 **Modificar el Inventario** (`inventory.ini`) para incluir las direcciones IP y usuarios correctos.
 
 **Ejecutar los Playbooks** en función de las necesidades:
   ```sh
   ansible-playbook -i inventory.ini web_setup.yml
   ansible-playbook -i inventory.ini hardening.yml
   ```
 
## Requisitos Previos
Para una correcta ejecución, asegúrate de contar con:
 
- **Ansible** instalado en la máquina desde donde se ejecutarán los comandos.
- **Servidores compatibles**: Mínimo uno con **CentOS Stream 9** y otro con **Ubuntu 24.04**.
- **Acceso remoto por SSH** con un usuario autorizado con permisos de `sudo`.
 
 
## Desarrolladores
Este proyecto fue realizado por:
 
- **Sol Varietti**
- **Caetano Rodriguez**