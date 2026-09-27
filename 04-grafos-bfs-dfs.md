# 04 — Grafos: BFS y DFS

Fuente conceptual: `03-grafos-representacion-y-recorridos.md` de
`repaso-entrevistas/bases/01-bases/04-arboles-grafos`.

## Cómo elegir

- ¿Solo importa si existe un camino? DFS o BFS.
- ¿Distancia mínima con todas las aristas de igual peso? BFS.
- ¿Componentes conectadas o regiones de una matriz? DFS/BFS.
- ¿Dependencias? Orden topológico.
- ¿Conjuntos que se unen y no necesitas recorrer caminos? Union-Find.

Para listas de adyacencia, piensa en O(V + E), no en O(V²), salvo que el enunciado pida una
matriz o el grafo sea muy denso.

## Problemas en orden

| Nivel | Problema | Patrón |
|---|---|---|
| Fácil | [Connected Cells in a Grid](https://www.hackerrank.com/challenges/connected-cell-in-a-grid/problem) | DFS/BFS en matriz |
| Medio | [Journey to the Moon](https://www.hackerrank.com/challenges/journey-to-the-moon/problem) | Componentes y conteo |
| Medio | [Roads and Libraries](https://www.hackerrank.com/challenges/torque-and-development/problem) | Componentes + coste |
| Difícil | [BFS: Shortest Reach in a Graph](https://www.hackerrank.com/challenges/ctci-bfs-shortest-reach/problem) | BFS y distancias |
| Medio | [Find the Nearest Clone](https://www.hackerrank.com/challenges/find-the-nearest-clone/problem) | BFS multi-origen |

## BFS en Java

```java
int[] dist = new int[n];
Arrays.fill(dist, -1);
ArrayDeque<Integer> queue = new ArrayDeque<>();
dist[start] = 0;
queue.add(start);

while (!queue.isEmpty()) {
    int u = queue.remove();
    for (int v : graph[u]) {
        if (dist[v] == -1) {
            dist[v] = dist[u] + 1;
            queue.add(v);
        }
    }
}
```

Nunca marques un nodo como visitado al sacarlo de la cola si eso puede introducir duplicados:
marcarlo al encolarlo mantiene el número de entradas controlado.

