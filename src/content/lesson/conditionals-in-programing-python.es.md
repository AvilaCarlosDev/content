---
date: "2026-08-21"
subtitle: "Domina condicionales en Python para controlar el flujo de tu código. Aprende a tomar decisiones programáticas y mejora tus habilidades de programación. Discover more!"
title: Condicionales en la programación en Python
author:
  - alesanchezr
syntax:
  - python
tags:
  - Condicionales
  - Operaciones lógicas
  - If...else
  - Condicion
  - Python
description: >-
  Domina condicionales en Python para controlar el flujo de tu código. Aprende a
  tomar decisiones programáticas y mejora tus habilidades de programación.
  Discover more!
---
## Introducción a los condicionales en Python 

Dominar el uso de las condiciones es una de las 5 habilidades fundamentales para construir algoritmos:

1. Variables.
2. Condicionales.
3. Listas.
4. Bucles (Loops).
5. Funciones.

El uso de *condicionales* es la única forma en que los desarrolladores tienen para decirle a la computadora cómo tomar decisiones en tiempo real.

Digamos que estamos construyendo un programa para ayudarnos a elegir qué ponernos y odiamos el color azul, podemos decirle a la computadora que evite el azul usando una condición como esta:
  
```python
if color == 'blue':
    # Haz algo
else:
    # Haz otra cosa
```
  
![Condicionales](https://github.com/breatheco-de/content/blob/master/src/assets/images/e73b673e-d744-45a7-a1ed-61a1dae49560.png?raw=true)

> 👉 El uso de `switch` no está disponible en Python

## Primero veamos ¿qué es una expresión lógica en Python?

La forma más fácil de entender expresiones lógicas (al menos para esta lectura en particular), es pensar en ellas como en preguntas que le puedes hacer al computador sobre nuestras variables, por ejemplo:

1. `if user_age > 21:`
2. `if day == "tuesday":`
3. `if car_model == "toyota" and number_of_tires == 6:`

Para hacer una pregunta, o excusar condicionalmente un conjunto particular de líneas, primero necesitas tener datos (información) almacenados en variables útiles, arriba tenemos las variables `user_age`, `day`, `car_model` y `number_of_tires`.

Si no tenemos la información prealmacenada en variables no podemos hacer ninguna pregunta, ¡todo es cuestión de estrategia y planificación!

Por ejemplo, si tenemos la edad del usuario almacenada en una variable `edad` entonces, y solo entonces, podremos codificar algo como:

```python
# Se utiliza dos veces igual (==) cuando quieres comparar en lugar de asignar el valor
if edad == 25:
    print("¡Eres mayor de edad!")
```

## ¿Qué tipo de condiciones/preguntas podemos usar/hacer?

El ejemplo anterior era una condición simple, pero en la vida real elegir qué ponerse implica una combinación de varias condiciones para tomar la decisión final, por ejemplo: Veamos este algoritmo que te dice si tienes gripe.

![Algoritmo de la gripe](https://github.com/breatheco-de/content/blob/master/src/assets/images/03ed6b76-0ee0-4b04-bd45-0fb58ae6f800.jpeg?raw=true)

Si desea representar este algoritmo en Python, se verá así:

```python runable=true
siento_que_me_atropello_un_tren = True
me_atropello_un_tren = False

if siento_que_me_atropello_un_tren == True:
    if me_atropello_un_tren == True:
        print("No tienes gripe")
    else:
        print("Tienes gripe")
else:
    print("No tienes gripe")
```

Básicamente, este algoritmo tiene dos variables a considerar: `siento_que_me_atropello_un_tren` y `me_atropello_un_tren`.
Nuestro trabajo como desarrolladores es sentarnos y tratar de preparar una estrategia para llegar a un algoritmo que resuelva un problema.

## Operadores lógicos en Python

Para hacer una pregunta, tenemos las siguientes comparaciones: `==`, `>`, `<`, `!=`, `is None`, `is not None`, `in`:

| Operador      | Ejemplo       | Descripción   |
| ------------  | -----------   | --------------|
| `==`          | `if a == b`   | Si el valor de la variable `a` es **igual** a `b` |
| `<`           | `if a < b`    | Si el valor de `a` es **menor** que `b` |
| `>`           | `if a > b`    | Si el valor de `a` es **mayor** que `b` |
| `!=`          | `if a != b`   | Si el valor de `a` es **diferente** de `b` |
| `is not None` | `if a is not None` | Si `a` es diferente de `None` |
| `is None`     | `if a is None`| Si el valor de `a` es igual a `None` |
| `in`          | `if name in ['bob','maria','nancy']` | Si el valor de `name` está contenido dentro de la lista de nombres  |

## Operadores `AND` y `OR` en Python

Otra forma de escribir el algoritmo es combinar preguntas en la misma condición utilizando los operadores `AND` y `OR`:

```python runable=true
siento_que_me_atropello_un_tren = True
me_atropello_un_tren = False

if siento_que_me_atropello_un_tren and me_atropello_un_tren:
    print("No tienes gripe")
elif siento_que_me_atropello_un_tren:
    print("Tienes gripe")
```

Como puedes ver, usamos `elif` por primera vez, para codificar más rápido. Otro truco que puedes usar es el siguiente:

| Original | Equivalente |
| --- | --- |
| En lugar de `if siento_que_me_atropello_un_tren == true` | escribes `if siento_que_me_atropello_un_tren` |
| En lugar de `if me_atropello_un_tren == false` | escribes `if not me_atropello_un_tren` |

## If...else en Python

También puedes usar la expresión `else` para referirte a la negación de la primera condición:

```python
if color "azul":
    # Descarta esta prenda de vestir
else:
    # Guárdala en mi armario
  
edad = 12
if (edad > 18):
    print("Es mayor de edad")
else:
    print("No es mayor de edad")
```

También puedes anidar condiciones if...else una sobre la otra, de esta forma:

```python
if edad < 16: 
    # No puedes hacer nada
elif age < 18:
    # A estas alturas, ya sabemos que es mayor de 15 porque si no, no hubiese ingresado a la primera condición
elif age < 21:
    # Si el algoritmo ingresa aquí, sabemos que es mayor de 17 
else:
    # Si el algoritmo ingresa aquí, sabemos que es mayor de 20
```

Aquí hay otro ejemplo que ejecuta un algoritmo para saber si un número tiene centenas:

```python runable=true
valor = 14

if valor < 10:
    print("El valor es una unidad")
elif valor < 100:
    print("El valor es una decena")
elif valor < 1000:
    print("El valor es una centena")
elif valor < 10000:
    print("El valor es una unidad de mil")
else:
    print("El valor es un número más allá de los miles")
```

> Cambia el valor de la variable `valor` para que veas como funciona con los diferentes valores.

## El `switch` en Python

Python no tiene una sentencia `switch` como otros lenguajes de programación.

## Conclusión

Hay que saber qué preguntas hacer. El ejemplo anterior era una condición simple, pero en la vida real, elegir qué hacer implica una combinación de varias condiciones para tomar la decisión final, por ejemplo: 

Veamos este algoritmo que le dice a una computadora cómo decidir qué ponerse durante el día de San Valentín:

![Qué ponerme en San Valentín](https://raw.githubusercontent.com/breatheco-de/content/refs/heads/master/src/assets/images/87f2be86-32c3-4bfc-8db4-dbd0d979e4d3.jpeg)

```python
if voy_a_salir:
    if puedo_comprar_hamburguesa:
        if venden_vino:
            # Haz algo
    else:
        if blazers > 3:
            # Haz algo
        else:
            # Haz algo
    elif usa_pantalones:
        # Haz algo
    else:
        # Haz algo
else:
    if desnudo_al_llegar:
        # Haz algo 
    elif blazers > 3:
        # Haz algo 
    else:
        # Haz algo 
```
