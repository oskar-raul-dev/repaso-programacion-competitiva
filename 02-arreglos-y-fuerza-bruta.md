# 02 — Arreglos y fuerza bruta

Fuente conceptual: `03-arrays-listas-y-secuencias.md` y `01-complejidad-y-o-grande.md` de
`repaso-entrevistas/bases/01-bases/01-fundamentos`.

## Qué dominar

1. Recorrido lineal y acumuladores.
2. Índices y recorrido inverso.
3. Matrices y ventanas de tamaño fijo.
4. Dos punteros en arreglos ordenados.
5. Sumas de prefijos para consultas de rango.
6. Fuerza bruta como solución de referencia: sirve para validar una optimizada en casos pequeños.

## Problemas de arreglos en orden

| Nivel | Problema | Patrón |
|---|---|---|
| Fácil | [Java 1D Array](https://www.hackerrank.com/challenges/java-1d-array-introduction/problem) | Crear, llenar y recorrer |
| Fácil | [Arrays Introduction](https://www.hackerrank.com/challenges/arrays-introduction/problem) | Recorrido inverso |
| Fácil | [Java 2D Array](https://www.hackerrank.com/challenges/java-2d-array/problem) | Ventana 3×3 / matriz |
| Fácil | [Java Subarray](https://www.hackerrank.com/challenges/java-subarray/problem) | Fuerza bruta sobre subarreglos |
| Fácil | [Java Arraylist](https://www.hackerrank.com/challenges/java-arraylist/problem) | Lista anidada y consultas |
| Fácil | [Sherlock and Array](https://www.hackerrank.com/challenges/sherlock-and-array/problem) | Suma total + suma izquierda |
| Medio | [Java 1D Array (Part 2)](https://www.hackerrank.com/challenges/java-1d-array/problem) | DFS/backtracking sobre índices |
| Medio | [Dynamic Array](https://www.hackerrank.com/challenges/dynamic-array/problem) | XOR, listas y consultas |
| Fácil | [Left Rotation](https://www.hackerrank.com/challenges/array-left-rotation/problem) | Índices circulares |
| Fácil | [Divisible Sum Pairs](https://www.hackerrank.com/challenges/divisible-sum-pairs/problem) | Pares y doble recorrido |
| Medio | [New Year Chaos](https://www.hackerrank.com/challenges/new-year-chaos/problem) | Recorrido local e inversiones |
| Medio | [Minimum Swaps 2](https://www.hackerrank.com/challenges/minimum-swaps-2/problem) | Posiciones y ciclos |
| Difícil | [Array Manipulation](https://www.hackerrank.com/challenges/crush/problem) | Diferencias y prefijos |

La selección coincide con el [kit oficial de Arrays de HackerRank](https://www.hackerrank.com/interview/interview-preparation-kit/arrays/challenges),
que agrupa `Left Rotation`, `New Year Chaos`, `Minimum Swaps 2`, `Array Manipulation` y `2D Array`.

## Problemas de fuerza bruta y backtracking

Aquí no buscamos la solución más rápida de inmediato. El objetivo es enumerar posibilidades,
entender el árbol de decisiones y detectar cuándo la fuerza bruta deja de ser viable.

| Nivel | Problema | Qué practicar |
|---|---|---|
| Fácil | [Java Subarray](https://www.hackerrank.com/challenges/java-subarray/problem) | Enumerar subarreglos |
| Fácil | [Divisible Sum Pairs](https://www.hackerrank.com/challenges/divisible-sum-pairs/problem) | Probar todos los pares |
| Medio | [The Power Sum](https://www.hackerrank.com/challenges/the-power-sum/problem) | Elegir/no elegir con recursión |
| Medio | [Building a List](https://www.hackerrank.com/challenges/building-a-list/problem) | Generar subconjuntos |
| Medio | [Java 1D Array (Part 2)](https://www.hackerrank.com/challenges/java-1d-array/problem) | DFS sobre estados |
| Difícil | [Crossword Puzzle](https://www.hackerrank.com/challenges/crossword-puzzle/problem) | Backtracking con restricciones |

Para cada uno registra dos versiones cuando tenga sentido: una enumeración simple y una mejora.
Por ejemplo, en pares empieza con O(n²); después prueba frecuencias por resto o un conjunto.

## Ejercicio de entrenamiento

Para cada problema escribe primero una versión deliberadamente simple. Después pregunta:

> ¿Qué trabajo se repite? ¿Puedo mantener el resultado al mover un índice? ¿Puedo precalcular?

Ejemplo de prefijos:

```java
long[] prefix = new long[n + 1];
for (int i = 0; i < n; i++) prefix[i + 1] = prefix[i] + a[i];
long sumLToR = prefix[r + 1] - prefix[l]; // intervalo inclusivo [l, r]
```

## Criterio de dominio

Puedes pasar a DP cuando resuelvas `Sherlock and Array`, `Java 2D Array` y `Divisible Sum Pairs` en menos de 15 minutos,
expliques por qué la solución es O(n) u O(n²), y detectes por ti mismo los casos de arreglo vacío,
un solo elemento, todos negativos y valores grandes.
