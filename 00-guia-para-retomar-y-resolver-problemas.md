# Guía para retomar y resolver problemas de HackerRank

Esta guía acompaña los problemas de:

- [Arreglos y fuerza bruta](02-arreglos-y-fuerza-bruta.md)
- [Programación dinámica](03-programacion-dinamica.md)

El objetivo no es resolver muchos problemas de forma superficial, sino aprender a reconocer el
patrón y explicar la solución con claridad durante una entrevista.

## Ruta enlazada para trabajar en HackerRank

Abre cada enlace con tu usuario de HackerRank y resuelve los problemas en este orden. No necesitas
crear archivos locales para enviar soluciones: este repositorio es el mapa de estudio y HackerRank
es el lugar donde ejecutas y envías el código.

### Fase 1 — arreglos y lectura de entrada

- [ ] [Java 1D Array](https://www.hackerrank.com/challenges/java-1d-array-introduction/problem) — crear y llenar un arreglo.
- [ ] [Arrays Introduction](https://www.hackerrank.com/challenges/arrays-introduction/problem) — recorrer e invertir.
- [ ] [Java 2D Array](https://www.hackerrank.com/challenges/java-2d-array/problem) — recorrer una matriz.
- [ ] [Java Arraylist](https://www.hackerrank.com/challenges/java-arraylist/problem) — listas de tamaño variable y consultas.
- [ ] [Left Rotation](https://www.hackerrank.com/challenges/array-left-rotation/problem) — índices circulares.

### Fase 2 — fuerza bruta y primera optimización

- [ ] [Java Subarray](https://www.hackerrank.com/challenges/java-subarray/problem) — enumerar subarreglos.
- [ ] [Divisible Sum Pairs](https://www.hackerrank.com/challenges/divisible-sum-pairs/problem) — probar pares y mejorar el conteo.
- [ ] [Sherlock and Array](https://www.hackerrank.com/challenges/sherlock-and-array/problem) — pasar de sumas repetidas a una suma total.
- [ ] [Dynamic Array](https://www.hackerrank.com/challenges/dynamic-array/problem) — listas, XOR y consultas.
- [ ] [The Power Sum](https://www.hackerrank.com/challenges/the-power-sum/problem) — recursión de elegir/no elegir.
- [ ] [Java 1D Array (Part 2)](https://www.hackerrank.com/challenges/java-1d-array/problem) — DFS y estados visitados.

### Fase 3 — programación dinámica

- [ ] [Max Array Sum](https://www.hackerrank.com/challenges/max-array-sum/problem) — DP 1D.
- [ ] [The Maximum Subarray](https://www.hackerrank.com/challenges/maxsubarray/problem) — Kadane y diferencia entre subarreglo y subsecuencia.
- [ ] [The Coin Change Problem](https://www.hackerrank.com/challenges/coin-change/problem) — contar formas con DP.
- [ ] [Construct the Array](https://www.hackerrank.com/challenges/construct-the-array/problem) — reducir estados y trabajar con módulo.
- [ ] [Abbreviation](https://www.hackerrank.com/challenges/abbreviation/problem) — DP sobre dos cadenas.
- [ ] [Candies](https://www.hackerrank.com/challenges/candies/problem) — restricciones locales y dos pasadas.

Después de completar esta ruta, continúa con [Array Manipulation](https://www.hackerrank.com/challenges/crush/problem)
y [Decibinary Numbers](https://www.hackerrank.com/challenges/decibinary-numbers/problem) como problemas de consolidación.

## Cómo usaremos HackerRank y este repositorio

1. Eliges el siguiente enlace de la ruta.
2. Intentas resolverlo en HackerRank durante 25–35 minutos.
3. Si pasas los tests, traes aquí el código y la explicación.
4. Si fallas, traes el mensaje de error, un caso que falla y tu código.
5. Si te atascas, puedes pedir una pista mínima sin que te dé la solución completa.
6. Tras resolverlo, marcamos la casilla y anotamos el patrón aprendido.

No hace falta que me compartas credenciales ni que yo entre a tu cuenta. Trabajaremos con el
enunciado, tu implementación y los resultados que HackerRank te muestre.

## 1. Cómo retomar después de varios días

Antes de abrir una solución, dedica 10 minutos a cada problema:

1. Lee solo el enunciado.
2. Escribe qué recibe la función y qué debe devolver.
3. Copia las restricciones importantes.
4. Resuelve un ejemplo pequeño a mano.
5. Escribe una fuerza bruta, aunque sea demasiado lenta.
6. Decide qué parte se repite o puede optimizarse.

Si no recuerdas nada del problema, eso es normal. Intenta reconstruirlo desde el enunciado; mirar
el nombre de la técnica demasiado pronto impide entrenar el reconocimiento.

## 2. Ficha de cada problema

Antes de programar, completa esta plantilla:

```text
Problema:
Entrada:
Salida:
Restricciones:
Casos borde:

Fuerza bruta:
Complejidad de la fuerza bruta:
Qué se repite:
Idea optimizada:
Complejidad final:
```

Después de resolverlo, añade:

```text
Patrón reconocido:
Error que cometí:
Pista que necesitaba:
Qué cambiaría en una segunda implementación:
```

## 3. El protocolo de los 30 minutos

### Minutos 0–5: entender

- Reescribe el problema con tus palabras.
- Comprueba si el arreglo es 0-indexado o 1-indexado.
- Identifica si se pide subarreglo contiguo o subsecuencia.
- Mira si hay varios casos de prueba.

### Minutos 5–10: estimar

Usa las restricciones para descartar soluciones:

| Tamaño aproximado | Solución que suele ser viable |
|---|---|
| `n <= 20` | Fuerza bruta, backtracking, `O(2^n)` |
| `n <= 500` | A veces `O(n²)` o DP 2D |
| `n <= 10^4` | `O(n²)` solo con cuidado |
| `n <= 10^5` | `O(n log n)` u `O(n)` |
| `n >= 10^6` | Normalmente `O(n)` o mejor |

Son reglas de orientación, no leyes: el límite real depende del lenguaje, las constantes y el
tiempo permitido.

### Minutos 10–20: diseñar

Explica en voz alta:

1. Qué representa cada variable.
2. Qué se mantiene cierto después de cada iteración.
3. Por qué no estás perdiendo una respuesta válida.
4. Qué ocurre en el primer y último elemento.

Si no puedes explicar el invariante, todavía no escribas el código final.

### Minutos 20–30: implementar y probar

Prueba primero el ejemplo del enunciado y luego estos casos:

- Un solo elemento.
- Arreglo vacío, si el contrato lo permite.
- Todos los valores iguales.
- Todos negativos.
- Valores en los extremos de las restricciones.
- Respuesta al principio y al final.
- Duplicados.

## 4. Cómo reconocer problemas de arreglos

| Señal del enunciado | Primera técnica que debes considerar |
|---|---|
| “Todos los pares” | Doble bucle; después hash o restos |
| “Subarreglo contiguo” | Ventana deslizante, prefijos o Kadane |
| “Arreglo ordenado” | Dos punteros o búsqueda binaria |
| “Muchas consultas de suma” | Sumas de prefijos |
| “Rotar o recorrer circularmente” | Índices módulo `n` |
| “Mínimo número de intercambios” | Posiciones, ciclos o inversiones |
| “Actualizar todos los valores entre `l` y `r`” | Arreglo de diferencias |

Pregunta clave:

> ¿Estoy recalculando información que ya conocía en la iteración anterior?

Si la respuesta es sí, busca una actualización incremental, prefijos o una estructura auxiliar.

## 5. Cómo trabajar la fuerza bruta

La fuerza bruta es tu primera versión de referencia, no una vergüenza.

Ejemplo para pares:

```java
for (int i = 0; i < n; i++) {
    for (int j = i + 1; j < n; j++) {
        // comprobar el par (i, j)
    }
}
```

Después analiza:

- ¿Puedo ordenar y usar dos punteros?
- ¿Puedo guardar lo visto en un `HashSet`?
- ¿Solo importa el resto módulo `k`?
- ¿La entrada es tan pequeña que `O(n²)` sí es suficiente?

En backtracking, dibuja el árbol de decisiones. Cada llamada debe dejar claro qué eliges, qué
exploras y qué deshaces.

## 6. Cómo reconocer programación dinámica

No uses DP solo porque el problema parece difícil. Busca estas dos señales:

1. El problema se divide en subproblemas del mismo tipo.
2. Los mismos subproblemas aparecen varias veces.

Usa este orden:

```text
estado → transición → casos base → orden de cálculo → memoria
```

Ejemplo para `Max Array Sum`:

```text
estado:       mejor suma usando el prefijo hasta i
decisiones:   tomar a[i] o no tomarlo
transición:   max(dp[i - 1], dp[i - 2] + a[i])
base:         prefijos de longitud 0 y 1
```

Primero escribe la tabla para una entrada pequeña. Si la tabla no tiene sentido, la definición del
estado todavía no está bien.

## 7. Cuándo pedir ayuda

Pega aquí el enunciado, tu intento y el punto exacto donde te bloqueaste. Puedes pedirme una ayuda
con uno de estos niveles:

- **Pista mínima:** una pregunta o señal, sin algoritmo.
- **Pista de patrón:** te digo si parece ventana, prefijos, backtracking o DP.
- **Diseño:** definimos el estado, la transición o el invariante.
- **Revisión:** reviso tu código y complejidad.
- **Solución completa:** vemos implementación y casos borde.

Para aprender más, empieza siempre por pista mínima.

## 8. Registro de progreso

Usa una tabla sencilla:

| Problema | Intento | Resultado | Patrón | Repetir |
|---|---:|---|---|---|
| Java 1D Array | 1 | Resuelto | Arreglo básico | 7 días |
| Java 2D Array | 1 | Con pista | Matriz/ventana | 2 días |
| Max Array Sum | 0 | Pendiente | DP 1D | Hoy |

Un problema cuenta como aprendido cuando puedes resolverlo de nuevo sin copiar, explicar la
complejidad y modificarlo ligeramente sin romper la solución.
