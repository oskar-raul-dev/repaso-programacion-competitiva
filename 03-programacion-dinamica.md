# 03 — Programación dinámica

Fuente conceptual: `01-programacion-dinamica.md` y `03-protocolo-de-pizarra.md` de
`repaso-entrevistas/bases/01-bases/05-dp-y-tecnicas`.

## Preguntas obligatorias

1. ¿Cuál es el estado mínimo que describe un subproblema?
2. ¿Qué decisiones puedo tomar desde ese estado?
3. ¿Cuál es la transición?
4. ¿Cuáles son los casos base?
5. ¿Qué orden permite calcular los estados?
6. ¿Puedo guardar solo las últimas filas o posiciones?

DP aparece cuando hay subproblemas solapados y subestructura óptima. Si no puedes definir un estado
claro, todavía no tienes una solución DP; no fuerces la técnica.

## Problemas en orden

| Nivel | Problema | Qué practicar |
|---|---|---|
| Medio | [Max Array Sum](https://www.hackerrank.com/challenges/max-array-sum/problem) | DP 1D: tomar/no tomar |
| Medio | [The Coin Change Problem](https://www.hackerrank.com/challenges/coin-change/problem) | Conteo de formas |
| Medio | [Candies](https://www.hackerrank.com/challenges/candies/problem) | DP en dos pasadas |
| Medio | [Abbreviation](https://www.hackerrank.com/challenges/abbreviation/problem) | DP sobre dos cadenas |
| Medio | [Construct the Array](https://www.hackerrank.com/challenges/construct-the-array/problem) | Estados agregados y módulo |
| Medio | [The Maximum Subarray](https://www.hackerrank.com/challenges/maxsubarray/problem) | Kadane: subarreglo y subsecuencia |
| Difícil | [Decibinary Numbers](https://www.hackerrank.com/challenges/decibinary-numbers/problem) | DP avanzada y precálculo |

La [ruta oficial de Dynamic Programming de HackerRank](https://www.hackerrank.com/interview/interview-preparation-kit/dynamic-programming/challenges)
incluye `Max Array Sum`, `Abbreviation`, `Candies` y `Decibinary Numbers`. Para preparar una
entrevista, resuelve primero los cuatro primeros de esta tabla y deja `Decibinary Numbers` para el
final.

## Plantilla mental: Max Array Sum

Para `a[i]`, define `dp[i]` como la mejor suma usando el prefijo hasta `i`. En cada posición:

```text
dp[i] = max(dp[i - 1], dp[i - 2] + a[i])
```

Antes de programar, resuelve el caso `[3, 7, 4, 6, 5]` a mano. Luego prueba negativos, ceros,
dos elementos y un elemento.

## Segundo bloque de práctica

Después de `Max Array Sum`, sigue este orden:

1. [The Maximum Subarray](https://www.hackerrank.com/challenges/maxsubarray/problem): distinguir subarreglo contiguo de subsecuencia.
2. [The Coin Change Problem](https://www.hackerrank.com/challenges/coin-change/problem): definir si `dp[x]` cuenta formas o calcula un mínimo.
3. [Construct the Array](https://www.hackerrank.com/challenges/construct-the-array/problem): reducir muchos valores a pocos estados agregados.
4. [Abbreviation](https://www.hackerrank.com/challenges/abbreviation/problem): tabla sobre dos índices.
5. [Candies](https://www.hackerrank.com/challenges/candies/problem): resolver restricciones desde ambos sentidos.

## Cómo revisar una solución DP

- ¿La transición usa estados ya calculados?
- ¿El caso base representa exactamente un prefijo vacío o de longitud 1?
- ¿La respuesta es `dp[n - 1]` o `dp[n]`?
- ¿El módulo se aplica después de cada suma?
- ¿La memoria puede reducirse de O(n) a O(1)?
