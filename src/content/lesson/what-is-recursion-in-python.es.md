---
date: "2026-08-21"
title: "¿Qué es la recursividad en Python?"
subtitle: "Descubre qué es la recursividad en Python. Explora la técnica de llamadas a sí mismo para resolver problemas complejos de manera elegante y eficiente."
tags: ["python", "recursividad-python"]
authors: ["DF27ARTS"]

---

## Explorando la Recursividad en Python  🔄🐍

La recursividad en la programación es una herramienta muy potente, esta se realiza con funciones que se llaman a sí mismas una y otra vez, puedes entenderlo como una especie de bucle que itera hasta que se cumple una condición. A continuación veremos un pequeño ejemplo donde usaremos una función recursiva para buscar el valor máximo en una lista de números.

```py runable=true
def encontrar_valor_maximo(lista):
    if len(lista) == 1:
        # Caso base o caso de salida
        return lista[0]
    else:
        # Caso recursivo
        lista_recortada = lista[1:]
        resultado = encontrar_valor_maximo(lista_recortada)
        if lista[0] > resultado:
            return lista[0]
        else:
            return resultado


lista = [1, 4, 25, 5, 7, 8, 9, 2, 40, 3, 27]
valor_maximo = encontrar_valor_maximo(lista)
print(f"El número máximo de la lista es: {valor_maximo}")
```

En este ejemplo hacemos uso de una función recursiva para encontrar el número más grande de una lista, en este código primero hacemos uso de una estructura condicional `if else` para verificar si el largo de la lista es igual a 1, de ser así retornamos el único número de la lista, este sería el caso de corte o caso base, de lo contrario, hacemos un llamado recursivo a la función `encontrar_valor_maximo()` y le pasamos por parámetro la lista menos el primer valor para ir recortando la lista en cada llamado recursivo y por último retornamos el valor máximo entre el primer número de la lista original y el resultado de la función.

## ¿Qué es la Recursividad en Python? 🔄🔍

La **recursividad** o recursión en un concepto que proviene de las matemáticas y que aplica al mundo de la programación, nos permite resolver problemas o tareas donde las mismas pueden ser divididas en sub tareas cuya funcionalidad es la misma. Dado que los subproblemas a resolver son de la misma naturaleza, se puede usar la misma función para resolverlos. En otras palabras, una función recursiva es aquella que está definida en función de sí misma, por lo que se llama repetitivamente a sí misma hasta llegar a un punto de salida.

Entenderás mejor cómo funciona la recursividad con la ayuda del siguiente video.

<iframe 
    width="560" 
    height="315" 
    src="https://www.youtube.com/embed/yX5kR63Dpdw" 
    title="La magia de la recursividad" 
    frameborder="0" 
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
    allowfullscreen
></iframe>

## El Caso Base ( La Clave para la Recursividad ) 🗝️🧩

El caso base es fundamental a la hora de trabajar con recursividad ya que define cuándo debe detenerse el proceso de llamadas recursivas. Si no defines un caso base adecuado, la función podría ejecutarse indefinidamente, agotando los recursos de tu ordenador y provocando un error en el sistema. 

Colocar un caso base incorrecto es un error muy común para alguien que empieza a trabajar con recursividad, así que recuerda bien que a la hora de crear una función recursiva lo primero que debes hacer antes de crear la lógica de la función es crear el caso base y asegúrate de que esté bien definido para evitar que la función se siga llamando a sí misma de forma indefinida.

| Característica | Descripción |
|-----------|--------------|
| Caso base | Nos permitirá terminar el ciclo de llamadas recursivas de la función en algún momento y que no entre en una pila de llamadas infinitas. |
| Caso recursivo | En el caso recursivo llamamos a la función una y otra vez en una pila de llamadas recursivas, pero nos iremos acercando a la solución de salida (el caso base). |

## Ventajas y Desventajas de la Recursividad 🌟📉

#### Ventajas

1. **Simplicidad conceptual**: Algunos problemas son naturalmente recursivos y se pueden resolver de manera más simple y elegante utilizando la recursividad.
2. **División de problemas**: La recursividad permite dividir un problema en subproblemas más pequeños, lo que facilita su resolución.
3. **Reducción de código**: En ciertos casos, el uso de la recursividad puede resultar en un código más conciso y legible en comparación con las soluciones iterativas.
4. **Aplicación en estructura de datos recursivas**: Las estructuras de datos cómo árboles y listas enlazadas a menudo se manejan de forma más natural y eficiente con enfoques recursivos.

#### Desventajas

1. **Consumo de memoria**: Las llamadas recursivas pueden llevar a un mayor uso de la memoria, ya que cada llamada agrega una nueva instancia en la pila de llamadas.
2. **Dificultad de seguimiento**: A veces, el flujo de ejecución en la recursividad puede ser difícil de seguir, lo que puede dificultar la depuración y comprensión del código.
3. **Tiempo de ejecución**: Las llamadas recursivas pueden llevar a un tiempo de ejecución más largo debido a la sobrecarga de llamadas y la necesidad de administrar la pila de llamadas.

## Ejemplos de Algoritmos Recursivos en Python 📝💡

A continuación veremos algunos ejemplos de algoritmos de recursividad en [Python](https://4geeks.com/es/lesson/como-programar-en-python).

### Cálculo Factorial

El cálculo factorial es un concepto matemático que implica multiplicar una seria de números consecutivos enteros positivos, comenzando desde **1** hasta un número **n**. Se reconoce por el símbolo "!", y se coloca después del número. Ejemplo:

```bash
// Factorial de N
n! = n * (n - 1) * (n - 2) * (n - 3) * ...

// Factorial de 5
5! = 5 * 4 * 3 * 2 * 1 = 120
```

Ejemplo de cálculo factorial haciendo uso de la recursividad con Python.

```py runable=true
def factorial(n):
    if n < 0:
        return "No se puede hacer un cálculo factorial con un número negativo"

    if n == 0 or n == 1:
        return 1
    else:
        return n * factorial(n - 1)

print(factorial(5))  # output: 120
print(factorial(3))  # output: 6
print(factorial(15))  # output: 1307674368000
print(factorial(-50))  # output: No se puede hacer un cálculo factorial con un número negativo
```

En este ejemplo, hacemos uso de la recursividad para encontrar el resultado factorial de un número **n**. Primero como en cualquier función de recursión, creamos el caso base con ayuda de un condicional `if else`, si el número **n** es igual a 0 o es igual a 1 entonces retornamos el número 1 y rompemos el ciclo de recursión, de lo contrario, llamamos a la función `factorial()` y le pasamos el número (n - 1) para encontrar el factorial de todos los números menores que **n** de forma recursiva y retornamos el resultado de la función multiplicado por **n**.

### Serie de Fibonacci

La serie de Fibonacci es una secuencia numérica en la que cada número es la suma de los dos números anteriores, la secuencia comienza con 0 y 1, luego cada número siguiente es la suma de los dos números previos, ejemplo:

```bash
0, 1, 2, 3, 5, 8, 13, 21, 34 ...
```

Ejemplo de una serie de fibonacci haciendo uso de la recursividad.

```py runable=true
def fibonacci(n):
    if n < 0:
        return "La serie de fibonacci solo acepta números positivos"
        
    lista_fibonacci = [0, 1]

    def recursion(numero, lista):
        if lista[-1] + lista[-2] > n:
            return lista
        else:
            lista.append(lista[-1] + lista[-2])
            return recursion(numero, lista)

    return recursion(n, lista_fibonacci)


numero_limite = 1000
resultado = fibonacci(numero_limite)
print("Serie fibonacci: ",  resultado)
```

En este ejemplo hacemos uso de recursión para encontrar todos los números de la serie de fibonacci menores que 1000, en este caso, el caso base es si la suma del dos últimos números de la lista es más grande que nuestro número límite **n**, de ser así, retornamos el array y terminamos la pila de llamadas recursivas, de lo contrario agregamos la suma de los dos últimos números a la lista y hacemos la llamada recursiva con la lista modificada una y otra vez hasta que la condición del caso base se cumpla.

### Suma de Números Naturales

La suma de números naturales se refiere a la adición de todos los números enteros positivos desde **1** hasta un número **n**. En términos matemáticos, se representa como la suma de una secuencia finita de números naturales. Ejemplo:

```bash
n = (n * n+1) / 2
n = n + (n - 1) + (n - 2) + ...

7 = (7 * 8) / 2 = 28
7 = 7 + 6 + 5 + 4 + 3 + 2 + 1 = 28
```

Ejemplo de suma de números naturales haciendo uso de una función recursiva.

```py runable=true
def suma_numeros_naturales(n):
    if n < 0:
        return "La suma de naturales sólo se puede hacer con números positivos"

    if n == 0:
        return 0
    else:
        return n + suma_numeros_naturales(n - 1)


print(suma_numeros_naturales(5)) # output: 15
print(suma_numeros_naturales(7)) # output: 28
print(suma_numeros_naturales(3)) # output: 6
print(suma_numeros_naturales(15)) # output: 120
print(suma_numeros_naturales(-20)) # output: La suma de naturales sólo se puede hacer con números positivos
```

En este ejemplo, el caso base es si el número ingresado por parámetro es igual a 0, de ser así, entonces retornamos 0 y terminamos la pila de llamadas recursivas, de lo contrario, llamamos a la función `suma_numeros_naturales()` de forma recursiva y le pasamos como parámetro el número `(n - 1)`, por último retornamos el resultado de la función más el número **n** esto nos dará la suma de todos los número desde **n** hasta **1**.

## Conclusión

La recursividad es una herramienta poderosa en la programación que permite resolver problemas dividiéndolos en subproblemas más pequeños. Al comprender de forma correcta el caso base y el caso recursivo, podemos crear algoritmos recursivos eficientes. La recursión es un tema complejo de la programación que requiere práctica para comprenderlo completamente, te recomiendo que practiques lo más que puedas realizando ejemplo cómo los vistos en este artículo. Puedes chequear el [Blog de 4Geeks](https://4geeks.com/es/) para aprender más contenido interesante.

¡Diviértete creando algoritmos de recursividad para tus propias aplicaciones! 😉
