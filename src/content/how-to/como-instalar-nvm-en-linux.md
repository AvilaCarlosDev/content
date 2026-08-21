---
subtitle: "Aprende cómo instalar NVM en Linux. Cubriendo distribuciones populares como Ubuntu y Fedora. Perfecto para desarrolladores que buscan manejar múltiples versiones de Node.js."
title: "¿Cómo Instalar NVM en Linux?"
description: "Aprende cómo instalar NVM en Linux. Cubriendo distribuciones populares como Ubuntu y Fedora. Perfecto para desarrolladores que buscan manejar múltiples versiones de Node.js."
authors: ["alesanchezr"]
tags: ['node', 'javascript', 'nvm']

---

Node Version Manager (NVM) es esencial para cualquier desarrollador que trabaje con Node.js. Te permite gestionar múltiples versiones activas de Node.js en un solo sistema. Esta guía proporciona instrucciones paso a paso sobre cómo instalar NVM en Linux, adaptándose a algunas de las distribuciones más comunes. Además, incluimos consejos de solución de problemas para los problemas más frecuentes que se encuentran durante la instalación.

> 💡 Esta guía es solo para sistemas Linux. Aquí tienes algunos enlaces si buscas una guía más general sobre [cómo instalar nvm en cada sistema operativo](https://4geeks.com/es/how-to/como-instalar-nvm-node-version-manager-en-cualquier-sistema-operativo) o específicamente [cómo instalar nvm en mac](https://4geeks.com/es/how-to/como-instalar-nvm-en-mac-os-node-js-y-npm) o [cómo instalar nvm en windows](https://4geeks.com/es/how-to/como-instalar-nvm-en-windows).

## Requisitos Previos

Antes de instalar NVM en tu sistema Linux, asegúrate de tener:

- Una distribución Linux estándar como Ubuntu, Debian, CentOS o Fedora.
- Utilidades básicas de línea de comandos instaladas.
- Acceso a una terminal.
- Privilegios de sudo para instalar paquetes.

## Instalación de nvm en Linux Ubuntu/Debian:

1. Abre tu terminal.
2. Instala `curl` o `wget` para descargar el script de instalación de NVM:
   ```bash
   $ sudo apt-get install curl
   ```
3. Descarga e instala NVM ejecutando:
   ```bash
   $ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
   ```
4. Carga tu perfil para agregar NVM a tu ruta:
   ```bash
   $ source ~/.profile
   ```

## Instalación de nvm en Linux CentOS/Fedora:

1. Abre tu terminal.
2. Instala `curl` o `wget`:
   ```bash
   $ sudo yum install curl
   ```
3. Descarga e instala NVM usando curl:
   ```bash
   $ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
   ```
4. Carga tu perfil bash:
   ```bash
   $ source ~/.bash_profile
   ```

### Verificar la Instalación

Después de la instalación, puedes verificar que NVM se haya instalado correctamente escribiendo:

```bash
$ nvm --version
```

Deberías ver el número de versión de NVM si la instalación fue exitosa.

![instalar nvm linux](https://github.com/breatheco-de/content/blob/master/src/assets/images/nvm-installation-success.png?raw=true)

## Pasos Comunes de Solución de Problemas

Instalar NVM (Node Version Manager) en Linux generalmente se realiza sin problemas, pero hay algunos problemas comunes que podrías encontrar. Aquí tienes una lista de estos posibles problemas junto con sus soluciones:

### 1. **Error de Comando No Encontrado Después de la Instalación**

**Problema:** 😱 Después de instalar NVM, cuando intentas usar comandos `nvm`, podrías encontrar un error `command not found`.
**Solución:** 😎 Este problema generalmente ocurre si el script de NVM no está cargado en el archivo de perfil de tu shell. Para solucionarlo, agrega las siguientes líneas a tu `.bashrc`, `.zshrc` o cualquier archivo de perfil de shell que uses:
   ```bash
   export NVM_DIR="$HOME/.nvm"
   [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # Esto carga nvm
   [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # Esto carga nvm bash_completion
   ```
   Después de agregar estas líneas, vuelve a cargar tu perfil con `source ~/.bashrc` (o el archivo respectivo), o reinicia tu terminal.

### 2. **El Script de Perfil No se Ejecuta al Iniciar la Terminal**

**Problema:** 😱 NVM no funciona automáticamente cuando abres una nueva ventana de terminal, incluso después de agregar las líneas necesarias a tu script de perfil.
**Solución:** 😎 Asegúrate de que tu terminal esté configurada para iniciar como un shell de inicio de sesión, ya que algunos sistemas o emuladores de terminal no lo hacen de forma predeterminada. Si usas GNOME Terminal u otro emulador, busca las preferencias de perfil o configuración y asegúrate de que la opción "Ejecutar el comando como un shell de inicio de sesión" esté marcada.

### 3. **Errores de Instalación Debido a curl o wget**

**Problema:** 😱 El script de instalación falla debido a problemas con `curl` o `wget`.
**Solución:** 😎 Asegúrate de que `curl` y `wget` estén instalados y actualizados en tu sistema. Puedes instalarlos a través de tu gestor de paquetes, por ejemplo:
   ```bash
   sudo apt install curl wget
   ```
   Luego, vuelve a intentar la instalación usando el comando de curl o wget.

### 4. **Problemas de Permisos Durante la Instalación**

**Problema:** 😱 El script de instalación de NVM falla con errores de permisos denegados.
**Solución:** Esto puede suceder si tu usuario no tiene permisos de escritura adecuados en el directorio de instalación o si intentas instalar sin privilegios suficientes. Ejecuta el script sin sudo, pero asegúrate de que tu usuario sea el propietario del directorio donde se está instalando NVM, generalmente tu directorio personal.

### 5. **Error de Instalación de Node Después de Instalar NVM**

**Problema:** 😱 Después de instalar NVM con éxito, intentar instalar versiones de Node da como resultado errores.
**Solución:** 😎 Esto podría deberse a problemas de red, o podrías estar detrás de un proxy. Si es un problema de proxy, configura npm para usar el proxy:
   ```bash
   npm config set proxy http://direccion-servidor-proxy:puerto
   npm config set https-proxy http://direccion-servidor-proxy:puerto
   ```
   Además, asegúrate de que no haya problemas de conectividad en tu red.

### 6. **NVM Lentifica la Inicialización de la Terminal**

**Problema:** 😱 Después de agregar NVM a tu script de perfil, la terminal se inicia significativamente más lenta.
**Solución:** 😎 NVM puede ralentizar el inicio de la terminal porque se engancha en el script de inicio del shell. Para aliviar esto, puedes cargar NVM de forma diferida o reducir la cantidad de procesos de shell que inicializa. Hay scripts y trucos comunitarios que pueden ayudar con la carga diferida de NVM, reduciendo su impacto en el tiempo de inicio del shell.

### 7. **Conflictos con Instalaciones Existentes de Node o NVM**

**Problema:** 😱 Surgen conflictos si hay restos de instalaciones previas de Node.js o NVM.
**Solución:** 😎 Elimina completamente cualquier instalación existente de Node.js (`sudo apt-get remove nodejs` y `sudo apt-get purge nodejs` para sistemas basados en Debian) y directorios de NVM (`rm -rf ~/.nvm`). Luego, intenta reinstalar NVM.

Estos pasos de solución de problemas deberían ayudarte a abordar los problemas más comunes al instalar NVM en sistemas Linux, asegurando un proceso de configuración más fluido para gestionar las versiones de Node.js.

## Instalación de NVM en Otros Sistemas Operativos

Si bien esta guía se centra en Linux, también es posible instalar NVM en otros sistemas operativos:

- Para usuarios de macOS, los pasos de instalación son similares a los de Linux. Instrucciones más detalladas se pueden encontrar en nuestra [guía dedicada a instalar NVM en macOS](https://4geeks.com/es/how-to/como-instalar-nvm-en-mac-os-node-js-y-npm).
- Los usuarios de Windows pueden usar NVM-Windows, una variante diferente adecuada para entornos Windows. Consulta nuestra [guía sobre cómo instalar NVM en Windows](https://4geeks.com/es/how-to/como-instalar-nvm-en-windows) para más información.

### ¿Qué es NVM?

NVM significa Node Version Manager. Como su nombre indica, te ayuda a gestionar y cambiar entre diferentes versiones de Node con facilidad. Es particularmente útil cuando gestionas múltiples proyectos que requieren diferentes versiones de Node.js, asegurando que se minimicen los problemas de compatibilidad.

### ¿Por Qué Instalar NVM en Linux?

Los usuarios de Linux se benefician de la flexibilidad de NVM, especialmente cuando trabajan en entornos de desarrollo que requieren ejecutar múltiples versiones de Node.js. Al instalar NVM en Linux, los desarrolladores pueden asegurarse de cambiar fácilmente entre proyectos sin problemas de compatibilidad.
