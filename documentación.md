# Obligatorio Febrero 2025 - Taller de servidores Linux 


![LogoORT!](/images/logort.png) 

|----------------------------------|-----------------------------------| **Sol Varietti - 288481 / Caetano Rodriguez - 241102** |

|----------------------------------|----------------------------------| **Profesor: Enrique Verdes / Fecha de entrega: 25/02/2025** |


----------------


## Introducción

A través de este documento presentamos el trabajo de fin de curso sobre la administración de servidores Linux mediante Ansible. El objetivo principal planteado en el obligatorio es aplicar los conocimientos adquiridos en la configuración y automatización de servidores usando Ansible, centrándose en la implementación de tareas en dos distribuciones diferentes: CentOS Stream 9 y Ubuntu 24.04.

El trabajo se compone de varias tareas que abarcan la configuración de inventarios, la ejecución de comandos ad-hoc, el desarrollo de playbooks y la documentación de los resultados. Para gestionar la labor de una mejor manera, se utilizará un repositorio GIT. 


### Tarea 1: Configuración del archivo de inventario 

En esta primera instancia se creará un archivo de inventario en formato INI, que permitirá a Ansible administrar los diferentes servidores agrupándolos en categorías. Se definirán las credenciales y direcciones IP necesarias para acceder a estos servidores.

**Archivo *inventory.ini***

En el siguiente archivo, ubicado dentro de la carpeta Inventories en el home del repositorio obligatorio2025, se definen los servidores administrados por Ansible. Este inventario está estructurado de acuerdo con los requisitos en la letra, creando los grupos Ubuntu y Centos , tomando en cuenta que contienen un host por grupo. Por otro lado, contamos con el grupo Linux, que contiene los subgrupos Ubuntu y Centos, y un grupo webserver, que también cuenta con el servidor Centos.

```python
    [centos]
    centos-srv ansible_host=192.168.56.20

    [ubuntu]
    ubuntu-srv ansible_host=192.168.56.10

    [linux:children]
    centos
    ubuntu

    [webserver]
    centos-srv

    [linux:vars]
    ansible_user=sysadmin
```

Además, el archivo define las variables *ansible_user* y *ansible_host*. Estas son vitales para establecer la conexión remota, dado que cada variable permite especificar el usuario para ejecutar las tareas de Ansible y la ip de cada servidor.

        Esto asegura la correcta comunicación entre el controlador y los nodos administrados???? 

**Prueba de conexión**

Se realizo una prueba de conexión con el fin de validar que los servidores son accesibles desde la maquina control (centos-srv). Para eso se utilizó el siguiente comando: 
```bash
    ansible all -i inventory.ini -m ping
```

El cual arrojo el siguiente resultado. 

![pruebadeconexión.t1](/images/pruebaconexion.png)



------


### Tarea 2: Ejecutar comandos ad-hoc
















