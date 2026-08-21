---
subtitle: "Aprende cómo instalar Git en Windows, macOS y Linux con esta guía completa. Instrucciones paso a paso para ayudarte a comenzar con Git."
title: "¿Cómo instalar Git en Windows, macOS y Linux?"
description: "Aprende cómo instalar Git en Windows, macOS y Linux con esta guía completa. Instrucciones paso a paso para ayudarte a comenzar con Git."
tags: ["git", "windows", "macos", "linux", "github"]
authors: ["alesanchezr"]

---

Git es una herramienta esencial para el control de versiones, ampliamente utilizada en la industria del desarrollo de software. Instalar Git en tu computadora te permite gestionar tu código de manera eficiente, colaborar con otros y mantener un historial de tus proyectos. 

> 💡 Este artículo trata sobre la instalación de Git, no sobre su uso. Haz clic aquí si estás buscando una guía completa sobre [cómo usar Git](https://4geeks.com/es/lesson/how-to-use-git-version-control-system-es) o [cómo clonar un repositorio de GitHub](https://4geeks.com/es/how-to/como-clonar-un-repositorio-de-github).

Este artículo proporciona una guía paso a paso para instalar Git en Windows, macOS y Linux.

## Instalación de Git en Windows

### Descargar el instalador

- Visita el sitio web oficial de Git: [Git para Windows](https://www.git-scm.com/download/win).
- Haz clic en el botón "Download" para obtener la última versión.

### Ejecutar el instalador

- Ubica el archivo `.exe` descargado y haz doble clic para ejecutarlo.
- Sigue las indicaciones de instalación. La configuración predeterminada es adecuada para la mayoría de los usuarios.

### Configurar Git

- Abre el Símbolo del Sistema o PowerShell.
- Establece tu nombre de usuario y dirección de correo electrónico:
  
```sh
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

## Instalación de Git en macOS

### Usando Homebrew

- Si no tienes Homebrew instalado, abre Terminal e instálalo:
  ```sh
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
  ```
- Instala Git usando Homebrew:
  ```sh
  brew install git
  ```

### Instalación manual

- Descarga el instalador más reciente de Git para macOS desde el sitio web oficial de Git: [Git para macOS](https://git-scm.com/download/mac).
- Abre el archivo `.dmg` descargado y sigue las instrucciones de instalación.

### Configurar Git

- Abre Terminal.
- Establece tu nombre de usuario y dirección de correo electrónico:
  ```sh
  git config --global user.name "Your Name"
  git config --global user.email "your.email@example.com"
  ```

## Instalación de Git en Linux (distribuciones basadas en Debian/Ubuntu)

### Actualizar la lista de paquetes

- Abre Terminal y ejecuta:
  ```sh
  sudo apt update
  ```

### Instalar Git

- Ejecuta el siguiente comando:
  ```sh
  sudo apt install git
  ```

## Instalación de Git en Linux (distribuciones basadas en Fedora)

### Instalar Git

- Abre Terminal y ejecuta:
  ```sh
  sudo dnf install git
  ```

## Instalación de Git en Linux (CentOS/RHEL-Based Distributions)

#### Habilitar el repositorio EPEL

- Abre Terminal y ejecuta:
  ```sh
  sudo yum install epel-release
  ```

#### Instalar Git

- Ejecuta el siguiente comando:
  ```sh
  sudo yum install git
  ```

### Configurar Git

- Abre Terminal.
- Establece tu nombre de usuario y dirección de correo electrónico:
  ```sh
  git config --global user.name "Your Name"
  git config --global user.email "your.email@example.com"
  ```

## Verificar la instalación de Git

Después de instalar Git, verifica que esté instalado correctamente ejecutando el siguiente comando en tu terminal o símbolo del sistema:

```sh
git --version
```

Deberías ver el número de versión de Git instalado.

## Git vs Github

Git y GitHub son cosas muy diferentes: el primero es una tecnología gratuita y de código abierto para rastrear los cambios de tu proyecto, y el segundo es una empresa con fines de lucro que utiliza Git (al igual que muchas otras empresas como GitLab y Bitbucket). Sin embargo, te recomendamos encarecidamente que entiendas qué es [Github](https://4geeks.com/es/lesson/bienvenido-a-github) y [cómo construir tu reputación de programación](https://4geeks.com/es/lesson/building-your-github-profile-and-reputation-es) en él porque te ayudará mucho a lo largo de tu carrera.

## Conclusión

Siguiendo estos pasos, deberías tener Git instalado en tu computadora, independientemente del sistema operativo. Configurar tu información de usuario de Git asegura que tus commits se atribuyan correctamente a ti. Con Git configurado, puedes comenzar a gestionar tus proyectos de manera más eficiente y colaborar con otros sin problemas.

- [Git para Windows](https://gitforwindows.org/)
- [Git para macOS](https://git-scm.com/download/mac)
