# 05 — Dijkstra y caminos mínimos

Fuente conceptual: `04-caminos-minimos-y-expansion-minima.md` de
`repaso-entrevistas/bases/01-bases/04-arboles-grafos`.

## Tabla de decisión

| Condición | Algoritmo |
|---|---|
| Sin pesos o todos pesan igual | BFS |
| Pesos no negativos, una fuente | Dijkstra |
| Puede haber pesos negativos, una fuente | Bellman–Ford |
| Todas las parejas y pocos nodos | Floyd–Warshall |
| Construir una red de coste mínimo | Prim o Kruskal |

Dijkstra se apoya en que, cuando extraes el menor candidato de la cola de prioridad, ningún
camino futuro con pesos no negativos puede mejorarlo. Por eso no es válido con pesos negativos.

## Problemas en orden

| Nivel | Problema | Qué practicar |
|---|---|---|
| Difícil | [Dijkstra: Shortest Reach 2](https://www.hackerrank.com/challenges/dijkstrashortreach/problem) | Lista de adyacencia + `PriorityQueue` |
| Medio | [Prim's (MST): Special Subtree](https://www.hackerrank.com/challenges/primsmstsub/problem) | MST con cola de prioridad |
| Medio | [Kruskal (MST): Really Special Subtree](https://www.hackerrank.com/challenges/kruskalmstrsub/problem) | Ordenar aristas + Union-Find |
| Difícil | [Floyd: City of Blinding Lights](https://www.hackerrank.com/challenges/floyd-city-of-blinding-lights/problem) | DP sobre parejas |

## Esqueleto de Dijkstra

```java
record Edge(int to, long weight) {}
record State(int node, long distance) {}

long[] dist = new long[n];
Arrays.fill(dist, Long.MAX_VALUE);
PriorityQueue<State> pq = new PriorityQueue<>(Comparator.comparingLong(State::distance));
dist[source] = 0;
pq.add(new State(source, 0));

while (!pq.isEmpty()) {
    State cur = pq.poll();
    if (cur.distance() != dist[cur.node()]) continue; // entrada obsoleta
    for (Edge edge : graph[cur.node()]) {
        long candidate = cur.distance() + edge.weight();
        if (candidate < dist[edge.to()]) {
            dist[edge.to()] = candidate;
            pq.add(new State(edge.to(), candidate));
        }
    }
}
```

La cola puede contener varias versiones del mismo nodo; no necesitas un `decreaseKey`. La
comparación con `dist` descarta las versiones viejas. En HackerRank, adapta `record` a clases
si el compilador configurado no acepta records.

