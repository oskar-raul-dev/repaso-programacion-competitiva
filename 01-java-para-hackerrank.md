# 01 — Java para HackerRank

## Plantilla base

```java
import java.io.*;
import java.util.*;

public class Solution {
    static final class FastScanner {
        private final InputStream in = System.in;
        private final byte[] buffer = new byte[1 << 16];
        private int ptr = 0, len = 0;

        private int read() throws IOException {
            if (ptr >= len) {
                len = in.read(buffer);
                ptr = 0;
                if (len <= 0) return -1;
            }
            return buffer[ptr++];
        }

        int nextInt() throws IOException {
            int c;
            do { c = read(); } while (c <= ' ' && c != -1);
            int sign = 1;
            if (c == '-') { sign = -1; c = read(); }
            int value = 0;
            while (c > ' ') {
                value = value * 10 + c - '0';
                c = read();
            }
            return value * sign;
        }
    }

    public static void main(String[] args) throws Exception {
        FastScanner fs = new FastScanner();
        StringBuilder out = new StringBuilder();
        // Leer, resolver y añadir a out. Imprimir una sola vez.
        System.out.print(out);
    }
}
```

## Decisiones que debes automatizar

| Necesidad | Java |
|---|---|
| Tamaño fijo y acceso por índice | `int[]`, `long[]` |
| Lista que crece | `ArrayList<Integer>` |
| Frecuencias o búsqueda promedio O(1) | `HashMap`, `HashSet` |
| Menor/mayor repetidamente | `PriorityQueue` |
| Grafo disperso | `List<int[]>[]` o `List<Edge>[]` |
| Salida grande | `StringBuilder` |

Usa `long` cuando una suma puede superar `2_147_483_647`, aunque cada elemento sea `int`.
Evita `Scanner` si la entrada es grande; el coste de parseo puede ser innecesario en una prueba.

## Checklist de compilación mental

- Índices: ¿el problema empieza en 0 o en 1?
- Límites: ¿el bucle usa `< n` y no `<= n`?
- Inicialización: ¿la respuesta funciona si todos los valores son negativos o cero?
- Desbordamiento: ¿la suma o la distancia necesita `long`?
- Grafo: ¿es dirigido/no dirigido? ¿hay aristas repetidas?
- Salida: ¿omite el nodo inicial? ¿requiere espacios o líneas exactas?

