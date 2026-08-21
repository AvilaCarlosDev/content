---
subtitle: "Aprende las bases de Python: sintaxis, bucles, tipos de datos y condicionales. ¡Descubre cómo este poderoso lenguaje puede transformar tu programación!"
title: ¿Qué es Python?
author:
  - alesanchezr
syntax:
  - python
tags:
  - Conditionals
  - Logical operators
  - Conditions
  - Python
description: >-
  Aprende las bases de Python: sintaxis, bucles, tipos de datos y condicionales.
  ¡Descubre cómo este poderoso lenguaje puede transformar tu programación!
---
# ¿Qué es Python?

Esta lección tiene como objetivo ayudar a familiarizarte con la sintaxis básica de Python y cómo hacer cosas esenciales como imprimir algo en un terminal, manipular strings y entender cómo se usan las variables, funciones, operaciones lógicas y condicionales. Esta debería ser la primera lección a leer en tu viaje con Python.

Por favor, sepa que hay otras lecciones explicando cada concepto en detalle; esto es solamente un resumen básico para ayudarte a obtener una visión general sobre el tema.

## ¿Por qué Python?

Python es el lenguaje backend de más rápido crecimiento en el mundo. Es el lenguaje más versátil y fácil de codificar, con una de las comunidades más sólidas.

Cuando lo comparas con otro lenguaje backend, Python es líder en casi todas las funcionalidades que ofrece: Data Science, IA, desarrollos de API, desarrollos web, redes, automatización, etc.

**Estas son algunas de las razones por las cuales Python ha llegado a este punto:**

|Simplicidad      |Rendimiento    |
|:---------------:|:------------------:|
|Python fue creado con la finalidad de ser simple y fácil. Aquí está el manifiesto de Python:<br>https://es.wikipedia.org/wiki/Zen_de_Python<br><br>**Nota:** No más puntos y comas, ni llaves, o declaración de variables, ni la confusa funcionalidad `this`.     | Python es más rápido que Java, PHP, Ruby y 90% de otros lenguajes backend. Solo lenguajes de bajo nivel como C++ (difícil de usar) o muy especializado como Node.js pueden vencerlo.<br><br>La escalabilidad de Python ha sido probada una y otra vez con aplicaciones como Google Search Engine, YouTube, Google Apps, etc.     |


|Comunidad        |Herramientas    |
|:---------------:|:------------------:|
|Python es el lenguaje oficial de Google. También es uno de los lenguajes más antiguos con comunidades muy grandes en torno a cada una de sus librerías/herramientas. MIT lo utiliza para codificar. La NASA para construir cohetes. Quora, Facebook, Yahoo, Amazon, etc. ¡Casi todas las grandes compañías del mundo deben usarlo!      |La mayoría de las librerías de Python son las mejores en lo que hacen: [MatLab](https://www.mathworks.com/help/matlab/matlab-engine-for-python.html?requestedDomain=true) (para procesamiento de datos), [Pandas](https://pandas.pydata.org/) (grandes datos), [Web.py](http://webpy.org/) (servidor web), [Django](https://www.djangoproject.com/) (web framework), [PyBrain](http://pybrain.org/) (IA), [TensorFlow](https://www.tensorflow.org/) (Machine Learning), etc.  ¡Podríamos estar en esto todo el día! Lo más asombroso es que estas librerías están a un `$ pip install` de poder usarlas (al igual que cuando se usa NPM con JS).|

## Sintaxis de Python

### Imprimiendo un valor

Una cosa esencial que puedes hacer en cualquier lenguaje de programación es imprimir algunos mensajes en el terminal. En Python puedes usar la instrucción `print` (imprimir):

```python runable=true
print("Hola, este es un mensaje que le puedes enseñar al usuario")
```

### Declarando una variable

Como la mayoría de los lenguajes de programación (o matemáticas), Python te permite almacenar datos en variables para poder utilizarlo posteriormente; las variables son una herramienta poderosa porque le permite a tu código ser reutilizado para cualquier valor de variable en el futuro, por ejemplo: para calcular un área cuadrada lo que tienes que hacer es:

```python runable=true
area = ancho * ancho
```
Tu código calculará el `area` sin importar el valor del `ancho`:

```python runable=true
# Si ancho=6 en el futuro
area = 6 * 6

# Si ancho=7 en el futuro
area = 7 * 7
```

> Las variables hacen tu código reutilizable y más dinámico.

### Imprimiendo una variable

También puedes imprimir (`print`) el valor almacenado en una variable, o incluso concatenarlo a otro string usando el operador más `+`:

```python runable=true
nombre = "Bob"
# Imprime solo el nombre
print(nombre) 
# O imprime un saludo que también incluya el nombre
print("Hola "+nombre+" ¿cómo estás?")
```

### Tipos de datos

Si no sabes o no lo recuerdas, los tipos de datos son tipos de información que puedes almacenar en una variable: números, texto, listas, etc. Cada lenguaje de programación tiene sus propios tipos de datos. En Python, estos son los tipos (hay más tipos que revisaremos más adelante):


| Tipo de Grupo		| Tipo				        | Descripción |
| -----------------	| ------------------------------------- | ----------------------------- |
| Tipos de Texto	| str					| Palabras, párrafos, etc. 	|
| Tipos Numéricos	| int, float, complex	| Operaciones matemáticas, etc.		|
| Tipos de Secuencia	| list, tuple, range	| Varios valores a la vez uno tras otro |
| Tipos Mapping	| dictionary			| Múltiples valores sin secuencia	|
| Tipo Boolean 	| bool				| Solo `True` o `False` |


### Convirtiendo tipos de datos

Es importante resaltar que el string `"1"` no es lo mismo que el número `1`, entonces, si quieres sumar `"1" + 1`, el resultado no será 2. En cambio, la computadora generará un error.

**¿Por qué?**

Porque los tipos de datos importan, tienes que ser consistente con ellos, si quieres sumar el string `5` con el string `2`, tienes que convertirlos en enteros primero, así:

```python runable=true
# En python, restar strings generará un error, en su lugar, deberías hacer: 
result = int('5') - int('2')
# La variable 'result' ahora es igual a 3
```
Por otra parte, si quieres sumar el string `"5"` con el string `"2"`, el resultado será `"52"` porque esa es la operación predeterminada para sumar strings: Concatenación.

> Hablaremos más sobre concatenación en otra lección.

### Listas y Tuplas 

Todos los principales lenguajes de programación tienen formas de almacenar listas de valores juntos; estos se llaman **listas** o **arrays** (matrices). 

Una lista de Python es una sucesión ordenada de valores, por ejemplo:

```python runable=true
edades = [23, 45, 34, 2, 65, 7, 32, 54, 3, 3, 6, 4]
nombres = ["Maria", "Willy", "Anyka", "Shan"]
```

Es importante recordar que el orden importa. Cada uno de los valores en una lista tiene una posición que siempre va a ser la misma. Puedes recuperar cualquier valor interno usando la posición que toman en la lista, por ejemplo:

```python runable=true
print(edades[0])  # Imprimirá 23 porque su posición es 0
print(edades[4])  # Imprimirá 65 porque su posición es 4
```
> Importante: las listas comienzan en la posición 0.

Las listas se utilizan ampliamente en todos los lenguajes de programación, especialmente en Python, porque Machine Learning utiliza enormes listas de información.

> Nota: vamos a discutir las listas en detalle pronto.

## Algoritmos de Python
 
Después de conocer lo básico de Python puedes empezar a construir algoritmos:
Un algoritmo es una sucesión de líneas de código con un propósito en común.
Las líneas de código van de arriba a abajo (desde la línea 1 hasta la línea N)
Por ejemplo, el siguiente es un algoritmo muy sencillo que imprime el nombre completo del nombre y apellido dados.

```python runable=true
nombre = "Taylor"
apellido = "Swift"

print("Miss " + nombre + " " + apellido)  # Imprime: Miss Taylor Swift
```

La primera línea es `nombre = "Taylor"` y se ejecuta primero; la última línea con la instrucción `print` ya sabe el valor de `nombre` porque fue completado primero (línea anterior).

### Condicionales

Las condiciones son fantásticas porque te permiten saltar o condicionalmente ejecutar partes de tu algoritmo, haciéndolos bastante flexibles e inteligentes. Por ejemplo, podríamos condicionalmente imprimir "Miss" (señorita) o "Mrs." (señora), dependiendo de su estado civil:

```python runable=true
estado_civil = "casada"
nombre = "Taylor"
apellido = "Swift"

if estado_civil == "soltera":
	print("Miss " + nombre + " " + apellido)  # Imprime: Miss Taylor Swift
else:
	print("Mrs. " + nombre + " " + apellido)  # Imprime: Mrs. Taylor Swift
```

> Nota: La instrucción `if...else` se lee como en inglés. También, para hacer comparaciones, debes utilizar dos signos de igual `==` en vez de uno, y a eso se le llama **Expresión Lógica**.

### Operaciones Lógicas y Expresiones

Las computadoras piensan todo en blanco o negro. Todo es o Verdadero o Falso. Todas las decisiones en una computadora se reducen a un simple **Booleano**. Puedes preparar una computadora para resolver problemas particulares, si escribes un código que haga las preguntas adecuadas requeridas para resolver ese problema.

Por ejemplo, si quiero que una computadora le dé caramelos solamente a niños mayores de 13 años, puedo indicarle a la computadora que pregunte:

**¿Es este niño mayor de 13 años?, ¿sí o no?**

**En Python, puedes indicarle a la computadora que haga las siguientes operaciones lógicas** 

|Operación      |Sintaxis       |Ejemplos   |
|:--------------|:--------------|:--------------|
|Igual a        |==             |¿Es 5 == 5? True!<br>¿Es 5 == 4? False!<br>¿Es 5 == '5'? False!    |
|No igual a     |!=             |¿Es 5 != 5? False!<br>¿Es 5 != '5'? True!<br>¿Es 1 != 'Hola'? True!   |
|Mayor que      |>              |¿Es 5 > 5? False!<br>¿Es 6 > 3? True!    |
|Menor que      |<              |¿Es 6 < 12? True!            |
|Mayor o igual a  |>=             |¿Es 6 >= 6? True!<br>¿Es 7 >= 6? True!    |
|Menor o igual a  |<=             |Ya entiendes la idea 🙂       |

Para crear operaciones realmente útiles, puedes combinar varias operaciones en la misma pregunta utilizando AND (y), OR (o) y NOT (no).

Puedes agrupar las operaciones lógicas en paréntesis, y también utilizar paréntesis anidados para varias operaciones al mismo tiempo.

|Operación       |Sintaxis       |Ejemplos   |
|:---------------|:--------------|:--------------|
|AND             |and            |Con AND, todas las operaciones DEBEN SER True para que el resultado final sea True.<br>¿Es (5 == 5 and 3 > 1)? True!<br>¿Es ('Ramon' == 'Pedro' and 2 == 2)? False!    |
|OR              |or             |Con OR, si al menos una de las operaciones es True, el resultado final será True.<br>¿Es ('Oscar' != 'Maria' or 2 != 2)? True!<br>¿Es (5 == '5' and 'Ramon' != 'Pedro') or (2 == 2)? True!   |
|NOT             |not            |NOT será el resultado opuesto al resultado del operador lógico:<br>¿Es not (5 > 5)? True!<br>¿Es not True? False!    |

## Controla el Flujo de Tu Código

Okey, ahora es cuando todo se empieza a poner ¡divertido! Para controlar el flujo de tus aplicaciones vas a tener muchas opciones y vas a usar cada una de ellas todos los días. Entonces, debes sentirte cómodo usándolas. 

### Condicionales: If...else

La primera herramienta que tienes es el condicional `if...else`. Puedes decirle a la computadora que se salte cualquier parte de tu código dependiendo del valor actual de tus variables.

La declaración `if` te permite ejecutar un pedazo de código si se cumplen ciertas condiciones (o son verdaderas). La declaración `else` va a ejecutar un pedazo de código alternativo en caso de que la condición sea falsa.

```python runable=true
numero = 17
if numero < 18:
	print("Esto se mostrará si el número es menor que 18")
else:
	print("El número es mayor o igual que 18")
```

### Loops (bucles)

El último truco que veremos hoy son los **loops**. Los loops son asombrosos porque te permiten repetir la ejecución de una o más líneas de código sin tener que escribir la misma línea varias veces:

```python runable=true
for n in range(10):
	print("Esta línea se imprimirá 10 veces")
```

También puedes hacerle loops a listas de valores:

```python runable=true
nombres = ["Bobby", "Diddi", "Kaylor"]
for n in nombres:
	print("El siguiente nombre es "+n)

# Esto imprimirá cada nombre en la consola
```

## ¿Listo para comenzar a aprender?

Por favor, no te abrumes, porque repasaremos cada uno de estos conceptos en las siguientes lecciones. ¡Obtendrás más oportunidades para practicar, aprender y liberar el potencial de tu mente!

