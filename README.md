# Repaso de programación competitiva en Java para entrevistas

Guía práctica para preparar pruebas técnicas ejecutadas en HackerRank: fundamentos de Java,
arreglos, fuerza bruta, ordenación/búsqueda, programación dinámica y grafos.

## Objetivo

Resolver problemas con un procedimiento repetible:

1. Leer restricciones y estimar la complejidad permitida.
2. Identificar la técnica: recorrido, dos punteros, ventana, prefijos, fuerza bruta, DP, BFS/DFS o Dijkstra.
3. Explicar la idea y los invariantes antes de escribir código.
4. Implementar en Java con entrada/salida robusta.
5. Probar casos borde y decir complejidad temporal y espacial.

Para retomar el estudio después de una pausa, empieza por la [guía de trabajo y resolución](00-guia-para-retomar-y-resolver-problemas.md).

## Contenido

| Fase | Guía | Resultado esperado |
|---|---|---|
| — | [Guía para retomar y resolver problemas](00-guia-para-retomar-y-resolver-problemas.md) | Ruta enlazada de HackerRank, ficha de problema, protocolo de 30 minutos y registro de progreso |
| 0 | [Java para HackerRank](01-java-para-hackerrank.md) | Leer input, colecciones y plantilla sin perder tiempo |
| 1 | [Arreglos y fuerza bruta](02-arreglos-y-fuerza-bruta.md) | Dominar índices, recorridos, simulación y optimizaciones básicas |
| 2 | [Programación dinámica](03-programacion-dinamica.md) | Reconocer estado, transición, casos base y optimización de memoria |
| 3 | [Grafos: BFS y DFS](04-grafos-bfs-dfs.md) | Representar grafos y resolver conectividad, componentes y distancias |
| 4 | [Dijkstra y caminos mínimos](05-dijkstra-y-caminos-minimos.md) | Elegir el algoritmo correcto según pesos y restricciones |

Este repositorio es el mapa de estudio: los problemas se resuelven y envían directamente en
HackerRank, sin necesidad de crear archivos locales de solución.

## Método de cada problema

- Antes de programar, completa la [ficha del problema](00-guia-para-retomar-y-resolver-problemas.md#2-ficha-de-cada-problema).
- Intento sin mirar solución: 25–35 minutos según dificultad, siguiendo el
  [protocolo de los 30 minutos](00-guia-para-retomar-y-resolver-problemas.md#3-el-protocolo-de-los-30-minutos).
- Si te atascas, escribe: entrada, salida, restricciones, fuerza bruta y qué la hace lenta.
- Pide una pista concreta aquí; no hace falta saltar directamente a la solución.
- Después de resolverlo, registra patrón, complejidad, bug cometido y una variante en el
  [registro de progreso](00-guia-para-retomar-y-resolver-problemas.md#8-registro-de-progreso).
- Repite el problema al día siguiente y una semana después, sin copiar el código.

## Tips para afrontar problemas

- **Restricciones primero.** El tamaño de `n` dice qué complejidad cabe: `n <= 20` admite
  `O(2^n)`, `n <= 10^5` pide `O(n log n)` u `O(n)`.
- **Fuerza bruta como referencia.** Escríbela aunque sea lenta; luego pregunta qué información
  estás recalculando que ya conocías.
- **Lee las señales del enunciado.** "Subarreglo contiguo" → ventana, prefijos o Kadane;
  "arreglo ordenado" → dos punteros o búsqueda binaria; "muchas consultas de suma" → prefijos;
  "actualizar rangos" → arreglo de diferencias.
- **DP solo con subproblemas repetidos.** Define estado → transición → casos base → orden de
  cálculo → memoria, y llena la tabla a mano para una entrada pequeña.
- **Explica el invariante antes de codificar.** Qué representa cada variable y qué se mantiene
  cierto tras cada iteración; si no puedes explicarlo, aún no escribas el código final.
- **Cuidado con los detalles.** Índices 0 vs. 1, subarreglo vs. subsecuencia, varios casos de
  prueba, desbordamiento de `int` (usa `long`).
- **Prueba casos borde.** Un solo elemento, todos iguales, todos negativos, duplicados, valores en
  los extremos y respuesta al principio o al final.
- **Pide ayuda por niveles.** Empieza por una pista mínima antes que por la solución completa.
- **No abras la solución** hasta haber escrito una explicación de 3–5 líneas y una complejidad
  estimada.
