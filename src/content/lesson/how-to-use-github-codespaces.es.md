---
title: "¿Por qué codificar en la nube en lugar de en tu computadora local?"
subtitle: "Descubre cómo usar GitHub Codespaces para el desarrollo en la nube. Aprende sus beneficios y mejora tu experiencia de codificación hoy mismo."
tags: ["git"]
description: >-
  Descubre cómo usar GitHub Codespaces para el desarrollo en la nube. Aprende
  sus beneficios y mejora tu experiencia de codificación hoy mismo.
---
Las empresas modernas ya no permiten a los desarrolladores trabajar en sus computadoras locales; usan entornos de desarrollo en la nube. Codespaces es la propuesta de GitHub para entornos de desarrollo en la nube.

> **En palabras simples**: Codespaces es una tecnología que crea *en cuestión de segundos*, computadoras y entornos de desarrollo en la nube, listos para ser usados por desarrolladores de software.

Al enseñar habilidades relacionadas con la programación, los entornos de desarrollo como Codespaces se han convertido en una de nuestras principales herramientas en 4Geeks. Como estudiante, se te anima a usar estos entornos, ya que acelerarán tu aprendizaje por lo menos en un orden de magnitud, eliminando toda la fricción que conlleva la configuración y permitiéndote enfocarte en tu código.

En esta lección, aprenderemos por qué los entornos de desarrollo en la nube se están volviendo una tendencia, sus beneficios y desventajas, y cómo usar GitHub Codespaces.

## ¿Por qué codificar en la nube en lugar de en tu computadora local?

Codificar en la nube tiene una limitación clave, que es requerir y depender de una conexión a internet, pero la tendencia es clara; la mayoría de las empresas estarán usando entornos en la nube en los próximos años. Pero, ¿por qué?

> ¿Alguna vez has intentado seguir un tutorial en línea, pero después de seguir a fondo cada paso, el código aún no se ejecuta en tu computadora?

La codificación en tu computadora local también trae limitaciones: las computadoras locales pueden romperse y el código puede perderse. Además, cada computadora local viene con diferentes sistemas operativos, versiones de Python, etc. Asegurarse de que su código sea compatible para ejecutarse en todas las computadoras puede ser un desafío e innecesario, ya que se publicará en una sola computadora: el entorno de producción.

## ¿Por qué Codespaces?

Codespaces es la propuesta de GitHub para la provisión de entornos de desarrollo. Esto simplifica dramáticamente el proceso de codificación, especialmente para los nuevos programadores.

Con Codespaces, puedes abrir cualquier repositorio en un entorno de desarrollo en la nube y comenzar o continuar codificando en segundos.

## ¿Cómo funciona Codespaces?

GitHub llama a cada entorno de codificación un "codespace". Si comienzas a trabajar en un proyecto y creas una nueva computadora en la nube para trabajar en tu proyecto, esta nueva computadora será un "codespace".

> 💻 Cada codespace es una computadora **virtual**.

- Tu lista de Codespaces (computadoras) actuales está aquí: [github.com/codespaces](https://github.com/codespaces). (Probablemente, esté vacío, ya que apenas estás aprendiendo sobre esto).
- La forma recomendada de crear un nuevo codespace es desde un repositorio de GitHub (si necesitas aprender qué es GitHub, piensa en él como una unidad de disco duro en línea de código, donde cada carpeta es uno de tus proyectos).

![Cómo abrir un codespace](https://github.com/breatheco-de/content/blob/master/src/assets/images/create-codespace.gif?raw=true)

- Una vez que el nuevo codespace se abra, creará una computadora vacía para ti, pero también descargará los archivos de la carpeta del repositorio de GitHub que especificaste (tu código) a esta nueva computadora.

- Finalmente, abrirá un editor de código (probablemente VSCode, el IDE de codificación más utilizado en el mundo) y una terminal para comenzar a codificar como si el codespace estuviera en tu computadora local desde el principio.

- Si vuelves a [tus Codespaces](https://github.com/codespaces), encontrarás todas las computadoras que has creado y podrás volver a abrirlas. Los cambios que hiciste en los archivos se mantendrán durante unos días; retendrás todos los datos siempre y cuando VUELVAS A ABRIR el mismo codespace en el que estabas trabajando o si desactivas la opción "Auto-delete codespace" en ese repositorio en específico.

## ¿Qué es un codespace de GitHub?

Es una computadora en la nube, lista para que comiences a codificar. Puedes volver a tu lista de Codespaces en cualquier momento y eliminar, renombrar o fijar cualquiera de ellos.

Cuando abres un repositorio de GitHub usando Codespaces, estarás "alquilando" una computadora con acceso al editor de código más popular del mundo: VSCode.

## Ejecutar un proyecto en Codespaces

Ve a cualquier repositorio de GitHub y podrás abrir un codespace haciendo clic en el botón de `Code -> Create codespace on <branch>`. Observa esta imagen:

![Abrir codespace en repositorio](https://github.com/breatheco-de/content/blob/master/src/assets/images/open-codespace.png?raw=true)

## La terminal

Como programador, a veces necesitas usar la terminal del computador; siempre puedes encontrar o abrir la terminal haciendo clic en el menú hamburguesa en la parte superior izquierda de VSCode y seleccionando la opción `Terminal -> Nuevo terminal`.

![Cómo abrir una terminal en VSCode](https://github.com/breatheco-de/content/raw/master/src/assets/images/terminal.png?raw=true)

## ¿Qué es la terminal o línea de comandos?

Todo computador tiene una terminal, y puedes usarla para hacer casi todo lo que quieras: abrir una aplicación, crear un archivo, carpeta, etc. Sin embargo, en Codespaces, la terminal solo controlará el computador virtual.

No tienes que aprender los comandos de la terminal todavía, pero [es muy recomendable leer esta lección](https://4geeks.com/es/lesson/the-command-line-the-terminal-es) para familiarizarte con ella y entender sus funciones y limitaciones.

![Terminal de VSCode](https://github.com/breatheco-de/content/blob/master/src/assets/images/terminal-command.png?raw=true)
