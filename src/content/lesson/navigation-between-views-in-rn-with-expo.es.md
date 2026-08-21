---
date: "2026-08-21"
subtitle: "Aprende a implementar navegación en React Native usando Expo Router y React Navigation. Descubre cómo estructurar rutas, pasar parámetros entre pantallas y elegir entre Stack y Tab navigation para crear apps móviles escalables y mantenibles."
title: "Domina la navegación entre vistas en React Native con Expo"
description: "Aprende a implementar navegación en React Native usando Expo Router y React Navigation. Descubre cómo estructurar rutas, pasar parámetros entre pantallas y elegir entre Stack y Tab navigation para crear apps móviles escalables y mantenibles."
author: "rosinni"
tags: ["React Native", "Expo", "Expo Router", "React Navigation", "TypeScript", "Desarrollo Móvil"]
---


Cuando comienzas a desarrollar con **React Native**, uno de los primeros retos que aparece es entender cómo funciona la **navegación entre pantallas**. En las apps móviles, moverse de una vista a otra no es un detalle menor: define la estructura completa de la experiencia del usuario.

En el ecosistema de React Native, la navegación se gestiona principalmente con dos herramientas: **React Navigation** y **Expo Router**. Ambas te permiten organizar tus pantallas, pasar datos entre ellas y definir flujos como pilas, pestañas o rutas anidadas.



## ¿Por qué necesitamos un sistema de navegación?

A diferencia del desarrollo web, donde un enlace cambia de página y el navegador mantiene el historial, en una app móvil todo ocurre dentro de una única aplicación. Por eso, necesitamos una **biblioteca de navegación** que gestione ese historial internamente, controle las transiciones y permita pasar parámetros entre pantallas.

React Native no trae navegación incorporada; la comunidad creó **React Navigation**. Con el tiempo, el equipo de Expo incorporó una versión simplificada llamada **Expo Router**, que elimina gran parte de la configuración manual y aprovecha la estructura de archivos del proyecto.


## Expo Router: el estándar moderno

**Expo Router** forma parte de las versiones más recientes de Expo. Su filosofía es simple: **la estructura de carpetas define tu navegación**. Cada archivo dentro del directorio `app/` se convierte automáticamente en una ruta o pantalla.

### 📁 Ejemplo de estructura

```bash
app/
 ├─ index.tsx        → Pantalla principal (/)
 ├─ profile.tsx      → Pantalla de perfil (/profile)
 ├─ settings/
 │   └─ index.tsx    → Pantalla de configuración (/settings)
 └─ _layout.tsx      → Layout común (navegación Stack o Tab)
```

No necesitas registrar manualmente cada pantalla ni definir rutas en un archivo central. Esto hace que el código sea más predecible, legible y fácil de escalar.


## Tipos de navegación: Stack y Tab

### Navegación tipo Stack

El patrón **Stack (pila)** es probablemente el más común. Imagina un conjunto de pantallas apiladas: cuando navegas a una nueva vista, se “empuja” encima de la anterior; al volver atrás, se “saca” de la pila.

```tsx
// app/_layout.tsx
import { Stack } from "expo-router";

export default function Layout() {
  return (
    <Stack>
      <Stack.Screen name="index" options={{ title: "Inicio" }} />
      <Stack.Screen name="profile" options={{ title: "Perfil" }} />
    </Stack>
  );
}
```

Cada archivo dentro de `app/` se transforma en una pantalla del stack. Esto facilita el flujo jerárquico: por ejemplo, desde una lista hacia un detalle.


### Navegación tipo Tab

Otro patrón clásico es la **navegación por pestañas**, muy común en apps con barra inferior. **Expo Router** también lo soporta a través del componente `Tabs`.

```tsx
// app/(tabs)/_layout.tsx
import { Tabs } from "expo-router";

export default function Layout() {
  return (
    <Tabs>
      <Tabs.Screen name="home" options={{ title: "Inicio" }} />
      <Tabs.Screen name="settings" options={{ title: "Configuración" }} />
    </Tabs>
  );
}
```

**Estructura típica:**

```bash
app/
 └─ (tabs)/
     ├─ _layout.tsx
     ├─ home.tsx
     └─ settings.tsx
```

Cada pestaña es una pantalla independiente, pero todas comparten el mismo layout inferior.


## Pasar datos entre pantallas

Una de las necesidades más comunes es **enviar información de una vista a otra**. Por ejemplo, al hacer clic en un usuario, queremos abrir su perfil y mostrar sus datos.

Con **Expo Router**, esto se logra de forma declarativa:

### Enlace con parámetros

```tsx
<Link href={{ pathname: "/profile", params: { userId: 42 } }}>
  Ver perfil
</Link>
```

### Recepción de parámetros

```tsx
import { useLocalSearchParams } from "expo-router";

export default function ProfileScreen() {
  const { userId } = useLocalSearchParams();
  return <Text>Perfil del usuario {userId}</Text>;
}
```

No hay magia; los parámetros se leen con un hook, igual que harías con props o query params en React. Esta forma de comunicación mantiene la aplicación modular y fácil de depurar.


## Tipado de rutas con TypeScript

Una de las mayores ventajas de trabajar con **Expo** y **React Native** en TypeScript es la posibilidad de **tipar tus rutas**. Esto evita errores comunes como pasar parámetros incorrectos o escribir mal un nombre de pantalla.

Puedes definir un tipo global de rutas:

```ts
export type RootStackParamList = {
  index: undefined;
  profile: { userId: number };
};
```

Ahora, cuando uses un enlace o una navegación, TypeScript te advertirá si envías un dato incorrecto:

```tsx
<Link href={{ pathname: "/profile", params: { userId: 42 } }} />
```

Si intentas pasar un texto en lugar de un número, el compilador lo marcará como error. Para quienes vienen de lenguajes fuertemente tipados como Kotlin o Swift, esto resulta natural: el tipado fuerte aporta seguridad y confianza en el código.


## ¿Cuándo usar cada tipo de navegación?

- Usa **Stack Navigation** cuando las pantallas sigan un flujo secuencial o jerárquico (inicio → detalle → confirmación).
- Usa **Tab Navigation** cuando tengas secciones independientes consultadas desde una barra inferior (inicio, perfil, ajustes).
- Usa **Expo Router** si trabajas con Expo y quieres una estructura limpia y predecible.
- Usa **React Navigation** si estás en un proyecto sin Expo o necesitas un control más granular sobre la configuración.


La navegación es el **esqueleto invisible** de toda aplicación móvil. En React Native, aprender a estructurarla correctamente marca la diferencia entre un proyecto improvisado y una app sólida, mantenible y escalable. **Expo Router** representa la evolución hacia una navegación declarativa y sencilla. Te permite concentrarte en construir experiencias y no en configurar rutas.

Y si vienes del mundo nativo (Kotlin o Swift), notarás algo familiar, cada vista sigue siendo una unidad independiente, pero ahora con la flexibilidad de React y la potencia de JavaScript.
