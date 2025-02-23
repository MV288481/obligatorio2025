# Obligatorio Febrero 2025 - Taller de servidores Linux 


![LogoORT!](/images/logort.png) 

|----------------------------------|-----------------------------------| **Sol Varietti - 288481** |

|----------------------------------|----------------------------------| **Profesor: Enrique Verdes / Fecha de entrega: 25/02/2025** |


----------------


## Introducción

Este documento presenta el trabajo de fin de curso sobre la administración de servidores Linux mediante Ansible. El objetivo principal es aplicar los conocimientos adquiridos en la configuración y automatización de servidores usando Ansible, centrándose en la implementación de tareas en dos distribuciones diferentes: CentOS Stream 9 y Ubuntu 24.04.

El trabajo se compone de varias tareas que abarcan la configuración de inventarios, ejecución de comandos ad-hoc, desarrollo de playbooks y documentación de los resultados. Se utilizará un repositorio GIT para gestionar el trabajo. 


### Tarea 1: Configuración del archivo de inventrio 

En esta tarea se creará un archivo de inventario en formato INI, que permitirá a Ansible gestionar los diferentes servidores agrupándolos en categorías. Se definirán las credenciales y direcciones IP necesarias para acceder a los servidores.

**Archivo *inventory.ini***

En el siguiente archivo, ubicado dentro de la carpeta Inventories en el home del repositorio obligatorio2025, se definen los servidores administrados por Ansible. Este inventario está estructurado de acuerdo con los requisitos en la letra, realizando la creación de los grupos Ubuntu y Centos y que contienen un host por grupo. Luego por otro lado, contamos con el grupo Linux, que contien los subgrupos Ubuntu y Centos, y un grupo webserver, con el servidor Centos.



    
    [centos]
    centos-srv ansible_host=192.168.56.20

    [ubuntu]
    ubuntu-srv ansible_host=192.168.56.10

    [linux:children]
    centos
    ubuntu

    [linux:vars]
    ansible_user=sysadmin


Además, el archivo define las variables *ansible_user* y *ansible_host*. Estas son vitales para establecer la conexión remota,cada variable permite especificar el usuario para ejecutar las tareas de Ansible y la ip de cada servidor.

        Esto asegura la correcta comunicación entre el controlador y los nodos administrados???? 

**Prueba de conexión**

Se realizo una prueba de conexión con el fin de validar que los seridores son accesibles desde la maquina control(centos-srv). Para eso se utilizo el siguiente comando: 

    ansible all -i inventory.ini -m ping

Lo que arrojo el siguiente resultado. 

![pruebadeconexión.t1](/images/pruebaconexion.png)














