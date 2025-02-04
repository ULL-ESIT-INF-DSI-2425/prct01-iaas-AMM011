# Informe de Práctica 1: Configuración de máquina virtual en el IaaS
### Autor: **Alfredo Moreno Mondragón**  
### Profesor: **Dr.Eduardo Manuel Segredo González**  
### Asignatura: **Desarrollo de Sistemas Informáticos**  
### Ubicación: **San Cristóbal de La Laguna**  
### Fecha: **02/02/2025**
### Índice: 
1. [Introducción](#1-introducción)
   - [Objetivo de la práctica](#objetivo-de-la-práctica)
2. [Requisitos previos](#2-requisitos-previos)
   - [Tareas previas](#tareas-previas)
3. [Acceso y configuración de la máquina virtual en el Servicio IaaS de la ULL](#3-acceso-y-configuración-de-la-máquina-virtual-en-el-servicio-iaas-de-la-ull)
   - [Configuración de la VPN de la ULL](#configuración-de-la-vpn-de-la-ull)
   - [Acceso al Servicio IaaS y asiganación de la máquina virtual](#acceso-al-servicio-iaas-y-asiganación-de-la-máquina-virtual)
   - [Conexión a la máquina virtual](#conexión-a-la-máquina-virtual)
4. [Configuración del nombre de host y del archivo de hosts](#4-configuración-del-nombre-de-host-y-del-archivo-de-hosts)
   - [Cambio del nombre de host en la máquina virtual](#cambio-del-nombre-de-host-en-la-máquina-virtual)
   - [Modificación del archivo de hosts en la máquina virtual](#modificación-del-archivo-de-hosts-en-la-máquina-virtual)
   - [Reinicio de la máquina virtual](#reinicio-de-la-máquina-virtual)
   - [Modificación del archivo de hosts en la máquina local](#modificación-del-archivo-de-hosts-en-la-máquina-local)
5. [Configuración de autenticación SSH con clave pública-privada](#5-configuración-de-autenticación-ssh-con-clave-pública-privada)
   - [Generación del par de claves en la máquina local](#generación-del-par-de-claves-en-la-máquina-local)
   - [Copia de la clave pública a la máquina virtual](#copia-de-la-clave-pública-a-la-máquina-virtual)
   - [Acceso SSH sin contraseña](#acceso-ssh-sin-contraseña)
   - [Configuración del alias SSH en la máquina local](#configuración-del-alias-ssh-en-la-máquina-local)
   - [Generación del par de claves en la máquina virtual](#generación-del-par-de-claves-en-la-máquina-virtual)
6. [Instalación y configuración de Git y Nodejs en la máquina virtual del IaaS](#6-instalación-y-configuración-de-git-y-nodejs-en-la-máquina-virtual-del-iaas)
   - [Instalación y configuración de Git](#instalación-y-configuración-de-git)
   - [Configuración del prompt de Git](#configuración-del-prompt-de-git)
   - [Autenticación SSH con GitHub](#autenticación-ssh-con-github)
   - [Clonación de repositorios desde GitHub](#clonación-de-repositorios-desde-github)
   - [Instalación y configuración de Nodejs con NVM](#instalación-y-configuración-de-nodejs-con-nvm)
7. [Conclusiones](#7-conclusiones)
   - [Evaluación de la práctica](#evaluación-de-la-práctica)
8. [Bibliografía y referencias](#8-bibliografía-y-referencias)  

# 1. Introducción
### Objetivo de la práctica
El objetivo principal de esta práctica es configurar una máquina virtual que sirva como entorno de desarrollo para el desarrollo de sistemas informáticos. 

En concreto, esta práctica permitirá:
- Familiarizarse con el uso de máquinas virtuales y su configuración básica.
- Aprender a instalar un sistema operativo en una máquina virtual.
- Configurar herramientas esenciales para el desarrollo de software.
- Garantizar la compatibilidad del entorno de desarrollo con futuras prácticas y proyectos.

# 2. Requisitos previos

Antes de iniciar con la configuración de la máquina virtual, llevamos a cabo una serie de tareas previas indicadas en el enunciado de la práctica. Estas acciones fueron fundamentales para garantizar un desarrollo fluido y estructurando de la activiidad.

### Tareas previas

1. **Cumplimentación de encuestas iniciales**  
   - Realizamos la encuesta de **elección de grupo de trabajo**.
   - Contestamos la encuesta sobre **expectativas y conocimientos previos**, proporcionando información sobre nuestra experiencia en el uso de máquinas virtuales y herramientas relacionadas.

2. **Configuración y uso de GitHub**  
   - Verificamos que disponíamos de una **cuenta de GitHub asociada a nuestro correo institucional** (aluXXXXXXXXXX@ull.edu.es).  
   - En caso de no contar con esta cuenta, procedimos a su creación.  
   - Solicitamos los beneficios de **GitHub Education**, lo que nos permitió acceder a herramientas adicionales para estudiantes.  
   - Nos dimos de alta en **GitHub Classroom** utilizando nuestra cuenta institucional de GitHub.  
   - Aceptamos la **asignación de GitHub Classroom** correspondiente a esta práctica, asegurándonos de tener acceso al repositorio necesario.  

3. **Preparación para la documentación en Markdown y GitHub Pages**  
   - Revisamos la **breve introducción a Markdown** proporcionada en el enunciado de la práctica, ya que se nos solicitó utilizar este lenguaje para redactar el informe.  
   - Consultamos el recurso sobre **GitHub Pages** y habilitamos la funcionalidad en el repositorio de la práctica, permitiendo que el informe se desplegara como una **GitHub Page**.  
   - Nos familiarizamos con **Jekyll**, la herramienta utilizada por GitHub Pages para transformar archivos Markdown en sitios web. Para ello, visitamos el sitio web oficial de [Jekyll](https://jekyllrb.com/).  

4. **Cursos recomendados de GitHub Skills**  
   Para mejorar nuestro manejo de GitHub y Markdown, completamos los siguientes cursos de **GitHub Skills**:
   - [Introduction to GitHub](https://skills.github.com/)
   - [Communicate using Markdown](https://skills.github.com/)
   - [GitHub Pages](https://skills.github.com/) *(incluye tópicos avanzados, aunque solo aplicamos lo necesario para desplegar nuestra GitHub Page).*

# 3. Acceso y configuración de la máquina virtual en el Servicio IaaS de la ULL

Antes de proceder con la configuración del entorno de desarrollo, llevamos a cabo la configuración de acceso al **Servicio IaaS de la ULL**, siguiendo los pasos detallados a continuación.

### Configuración de la VPN de la ULL
Para acceder a las máquinas virtuales del **Servicio IaaS de la ULL** desde fuera de la red universitaria, configuramos el servicio **VPN de la ULL** en nuestro equipo.

1. Accedimos a la documentación oficial de la ULL sobre la configuración de la VPN.

2. Descargamos las instrucciones y el software correspondiente según nuestro sistema operativo.

3. Instalamos y configuramos la VPN siguiendo las indicaciones proporcionadas.

4. Establecimos la conexión con la VPN, verificando que el acceso a la red universitaria estaba correctamente habilitado.

Este paso resultó crucial, ya que sin la conexión a la VPN, el acceso al Servicio IaaS no era posible, si no nos encontramos en al universidad.


### Acceso al Servicio IaaS y asiganación de la máquina virtual
Una vez conectados a la VPN, accedimos al **Servicio IaaS de la ULL** mediante el portal web oficial e iniciamos sesión con nuestras credenciales de la universidad.

1. Accedimos al panel de control, donde se nos mostró una lista de las máquinas virtuales asociadas a nuestra cuenta.

2. En caso de no contar con una máquina virtual asignada, tomamos una del **pool denominado DSI**.

3. Tras completar la asignación, nuestra máquina pasó a tener un identificador único con un sufijo numérico, por ejemplo, **DSI-52**.

4. Monitoreamos los estados de la máquina virtual hasta que cambió a **"En ejecución"**, momento en el cual quedó lista para su uso.

### Conexión a la máquina virtual
Con la máquina virtual en estado **"En ejecución"**, procedimos a conectarnos a la misma utilizando la **Consola VNC** a través del navegador.

1. Iniciamos sesión con las credenciales predeterminadas:
   - **Usuario:** `usuario`
   - **Contraseña:** `usuario`

2. Inmediatamente, el sistema solicitó el cambio de contraseña por motivos de seguridad. Introdujimos una nueva contraseña y la almacenamos en un lugar seguro.

3. Para verificar la configuración de red de la máquina virtual, ejecutamos los siguientes comandos en la terminal:

   ```bash
   sudo apt install net-tools
   ifconfig -a
   ```

# 4. Configuración del nombre de host y del archivo de hosts
Una vez establecida la conexión con la máquina virtual, procedimos a modificar el **nombre de host** para personalizar la identidad de la máquina dentro de la red universitaria. También realizamos cambios en el archivo **/etc/hosts** tanto en la máquina virtual como en la máquina local, con el fin de facilitar la conexión SSH sin necesidad de recordar la dirección IP.

### Cambio del nombre de host en la máquina virtual

El nombre de host predeterminado era `ubuntu`, por lo que lo modificamos a `iaas-dsi-amm011` con los siguientes pasos:

1. Consultamos el nombre de host actual:
   ```bash
   cat /etc/hostname
   ```

2. Editamos el archivo para modificar el nombre de la máquina:
   ```bash
   sudo vi /etc/hostname
   ```
   Reemplazamos `ubuntu` por `iaas-dsi-amm011` y guardamos los cambios.

3. Verificamos la modificación:
   ```bash
   cat /etc/hostname
   ```

### Modificación del archivo de hosts en la máquina virtual 

Para evitar inconsistencias en la resolución de nombres dentro de la máquina virtual, actualizamos el archivo `/etc/hosts` con la siguiente información:

1. Consultamos su contenido actual:
   ```bash
   cat /etc/hosts
   ```

2. Editamos el archivo:
   ```bash
   sudo vi /etc/hosts
   ```
   Reemplazamos `ubuntu` por `iaas-dsi-amm011` y guardamos los cambios:
   ```
   127.0.1.1 iaas-dsi-amm011
   ```

3. Verificamos los cambios:
   ```bash
   cat /etc/hosts
   ```

### Reinicio de la máquina virtual

Para aplicar los cambios realizados, reiniciamos la máquina virtual con el siguiente comando:

```bash
sudo reboot
```
### Modificación del archivo de hosts en la máquina local

Los pasos a realizar en la máquina local son los mismos que en la máquina virtual, pero con la dirección IP de la máquina virtual y el nombre de host correspondiente.

Con esta configuración, pudimos acceder a la máquina virtual mediante SSH utilizando el nombre de host `iaas-dsi-amm011` en lugar de la dirección IP, de esta manera:

```bash
ssh usuario@iaas-dsi-amm011
```

# 5. Configuración de autenticación SSH con clave pública-privada

Para facilitar el acceso a la máquina virtual sin necesidad de ingresar una contraseña en cada conexión SSH, configuramos la autenticación basada en clave pública-privada. Esto mejora la seguridad y la eficiencia al conectarnos a la máquina remota.

### Generación del par de claves en la máquina local

Antes de generar un nuevo par de claves, verificamos si ya existía una clave pública en nuestra máquina local:

```bash
cat ~/.ssh/id_rsa.pub
```

- Si el archivo existía, significaba que ya teníamos un par de claves y podíamos reutilizarlo.
- Si el archivo no existía, generamos un nuevo par de claves con el siguiente comando:

```bash
ssh-keygen
```

### Copia de la clave pública a la máquina virtual

Para permitir la autenticación sin contraseña, copiamos la clave pública a la máquina virtual:

```bash
ssh-copy-id usuario@iaas-dsi-amm011
```

- Ingresamos la contraseña de la máquina virtual cuando se nos solicite.
- Tras ingresarla correctamente, la clave quedó instalada en la máquina virtual.

### Acceso SSH sin contraseña

Verificamos que la autenticación mediante clave pública-privada estaba funcionando correctamente intentando acceder a la máquina virtual:

```bash
ssh usuario@iaas-dsi-amm011
```

- Si no se nos solicitó la contraseña, la autenticación fue exitosa.

### Configuración del alias SSH en la máquina local

Para evitar tener que escribir el nombre de usuario en cada conexión SSH, configuramos un alias en la máquina local:

1. Creamos el archivo de configuración SSH si no existía:

```bash
touch ~/.ssh/config
```

2. Editamos el archivo de configuración:

```bash
vi ~/.ssh/config
```

3. Añadimos la siguiente configuración:

```bash
Host iaas-dsi-amm011
  HostName iaas-dsi-amm011
  User usuario
```

4. Guardamos los cambios y verificamos la configuración con:

```bash
cat ~/.ssh/config
```

A partir de este momento, pudimos conectarnos a la máquina virtual simplemente ejecutando:

```bash
ssh iaas-dsi-amm011
```

### Generación del par de claves en la máquina virtual

Para asegurar una comunicación segura con otros servidores, también generamos un par de claves en la máquina virtual:

```bash
ssh-keygen
```

Durante la generación de claves:

- Se aceptaron las opciones por defecto.
- No se introdujo ninguna passphrase.

Verificamos la clave pública recién creada con:

```bash
cat ~/.ssh/id_rsa.pub
```

# 6. Instalación y configuración de Git y Nodejs en la máquina virtual del IaaS

Para gestionar versiones de código y configurar el entorno de desarrollo en la máquina virtual, instalamos y configuramos **Git** y **Node.js**, asegurando su correcta integración con GitHub mediante SSH.

### Instalación y configuración de Git

En primer lugar, verificamos si **Git** estaba instalado en la máquina virtual ejecutando:

```bash
git --version
```

Si Git no estaba instalado, procedimos con su instalación:

```bash
sudo apt update
sudo apt install git
```

Al ejecutar el comando, el sistema mostró que la versión más reciente de Git ya estaba instalada.

Posteriormente, realizamos la configuración inicial de Git estableciendo nuestro nombre de usuario y correo electrónico:

```bash
git config --global user.name "Alfredo Moreno"
git config --global user.email "alu0101515601.ull.edu.es"
```

ara verificar la configuración, ejecutamos:

```bash
git config --list
```

La salida confirmó que la información fue almacenada correctamente.

### Configuración del prompt de Git

Para visualizar la rama activa de un repositorio Git en el prompt de la terminal, descargamos y configuramos el script git-prompt.sh:

1. Descargamos el script desde el repositorio oficial de Git:

```bash
wget https://raw.githubusercontent.com/git/git/master/contrib/completion/git-prompt.sh
```

2. Movimos el archivo a nuestra carpeta personal y lo renombramos:

```bash
mv git-prompt.sh ~/.git-prompt.sh
```

3. Editamos el archivo ~/.bashrc para cargar el script y modificar el **prompt**:

```bash
vi ~/.bashrc
```

4. Agregamos las siguientes líneas al final del archivo:

```bash
source ~/.git-prompt.sh
PS1='\[\033]0;\u@\h:\w\007\]\[\033[0;34m\][\[\033[0;31m\]\w\[\033[0;32m\]($(git branch 2>/dev/null | sed -n "s/\* \(.*\)/\1/p"))\[\033[0;34m\]]$ '
```

5. Reiniciamos la terminal para aplicar los cambios.

```bash
exec bash -l
```

Con esta configuración, el prompt mostró la rama activa cuando accedimos a un directorio con un repositorio Git.

### Autenticación SSH con GitHub

Para evitar ingresar credenciales en cada interacción con GitHub, añadimos la clave pública de la máquina virtual a nuestra cuenta de GitHub:

1. Obtenemos la clave pública generada en la máquina virtual:

```bash
cat ~/.ssh/id_rsa.pub
```

2. Copiamos la clave y accedimos a GitHub > Settings > SSH and GPG keys.

3. Agregamos una nueva clave SSH pegando el contenido copiado.

4. Para probar la conexión SSH con GitHub, ejecutamos:

```bash
ssh -T git@github.com
```

### Clonación de repositorios desde GitHub

Para confirmar la autenticación SSH y probar el entorno Git, clonamos un repositorio privado del curso:

```bash
git clone git@github.com:ULL-ESIT-INF-DSI-2425/prct01-iaas-alu0101515601.git
```

### Instalación y configuración de Nodejs con NVM

1. Para gestionar versiones de Node.js, instalamos NVM (Node Version Manager):

```bash
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

2. Tras la instalación, aplicamos los cambios recargando la terminal:

```bash
exec bash -l
```

3. Verificamos la instalación de **NVM** con:

```bash
nvm --version
```

4. Luego, instalamos la última versión de **Node.js**:

```bash
nvm install node
```

5. Para confirmar la instalación, verificamos las versiones de Node.js y npm:

```bash
node --version
npm --version
```

Si necesitábamos instalar una versión específica, ejecutamos:

```bash
nvm install <version>
```

Finalmente, listamos todas las versiones disponibles y seleccionamos una específica con:

```bash
nvm list
nvm use <version>
```

Con esta configuración, la máquina virtual quedó lista para el desarrollo con Git y Node.js, facilitando la gestión de repositorios y el uso de versiones específicas del entorno.

# 7. Conclusiones

Al finalizar esta práctica, logramos configurar con éxito una máquina virtual en el servicio **IaaS de la ULL**, estableciendo un entorno de desarrollo funcional. La práctica nos permitió familiarizarnos con la infraestructura del servicio, la gestión de máquinas virtuales y la configuración de herramientas esenciales como **Git** y **Node.js**.

### Evaluación de la práctica

La práctica resultó fundamental para comprender la importancia de trabajar con **infraestructura virtualizada** en un entorno académico. A lo largo de la realización, enfrentamos y superamos diversos retos, tales como:

- La **configuración de la VPN de la ULL**, necesaria para acceder al servicio IaaS desde fuera de la red universitaria.
- La **gestión de la máquina virtual**, incluyendo la asignación de recursos y la configuración del sistema operativo.
- La **configuración del acceso SSH**, permitiendo la autenticación mediante clave pública-privada sin necesidad de introducir credenciales en cada conexión.
- La **instalación y personalización de Git**, lo que facilitó el control de versiones y la integración con **GitHub** mediante SSH.
- La **instalación y configuración de Node.js** utilizando **NVM**, lo que permitió gestionar diferentes versiones del entorno de desarrollo.

Cada uno de estos pasos reforzó el uso de herramientas clave en el desarrollo de software y nos permitió optimizar el flujo de trabajo en un entorno virtualizado.

# 8. Bibliografía y referencias

- **Enunciado de la Práctica 1**  
  - Práctica 1: Configuración de máquina virtual en el IaaS. Disponible en: [https://ull-esit-inf-dsi-2425.github.io/prct01-iaas/](https://ull-esit-inf-dsi-2425.github.io/prct01-iaas/)

- **VPN de la ULL**  
  - Configuración de la VPN de la ULL. Disponible en: [https://www.ull.es/servicios/stic/2024/11/29/servicio-de-vpn-de-la-ull/](https://www.ull.es/servicios/stic/2024/11/29/servicio-de-vpn-de-la-ull/)

- **Servicio IaaS de la ULL**  
  - Universidad de La Laguna. Disponible en: [https://iaas.ull.es/](https://iaas.ull.es/)

- **Markdown y GitHub Pages**  
  - Introducción a Markdown. Disponible en: [https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
  - Documentación de GitHub Pages. Disponible en: [https://docs.github.com/en/pages](https://docs.github.com/en/pages)
  - Jekyll – Generador de sitios estáticos para GitHub Pages. Disponible en: [https://jekyllrb.com/](https://jekyllrb.com/)

- **GitHub Skills**
   - GitHub Skills. Disponible en: [https://skills.github.com/](https://skills.github.com/)
