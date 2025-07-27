# Semana 2

# Algoritmos Voraces y Grafos

## 1. Algoritmos Voraces

### 1.1 Definición
Un **algoritmo voraz** es una estrategia de diseño de algoritmos que construye una solución de manera incremental, 
seleccionando en cada paso la **opción localmente óptima**, con la esperanza de que dicha elección conduzca a una **solución globalmente óptima**.  
Estos algoritmos son apropiados únicamente para problemas que presentan **subestructura óptima** y cumplen con la **propiedad de elección voraz**.

Ejemplos representativos:
- Algoritmo de **Dijkstra** para la obtención de caminos mínimos.
- Algoritmos de **Kruskal** y **Prim** para la construcción de árboles generadores mínimos.
- Problemas de **cambio de monedas** en sistemas monetarios canónicos.

---

### 1.2 Ventajas
- Implementación relativamente sencilla y de fácil comprensión.
- Bajo consumo de memoria en comparación con algoritmos de búsqueda exhaustiva.
- Alta eficiencia temporal en problemas adecuados para esta estrategia.

---

### 1.3 Desventajas
- No garantiza la obtención de la solución óptima en todos los casos.
- Aplicabilidad limitada a problemas que cumplan propiedades específicas.
- Puede producir soluciones subóptimas cuando la elección local no conduce a la global.

---

## 2. Grafos

### 2.1 Definición
Un **grafo** es una estructura matemática definida como un par ordenado:

\[
G = (V, E)
\]

donde:
- \( V \) es un conjunto no vacío de **vértices** o **nodos**.
- \( E \) es un conjunto de **aristas** o **arcos**, que son pares de elementos de \( V \).

---

### 2.2 Grafos conexos y no conexos
- **Grafo conexo:** existe un camino entre todo par de vértices de \( G \).
- **Grafo no conexo:** contiene al menos dos vértices entre los cuales no existe camino.

---

### 2.3 Grafos dirigidos y no dirigidos
- **Grafo dirigido (dígrafo):** las aristas tienen orientación, representadas como pares ordenados \( (u,v) \).
- **Grafo no dirigido:** las aristas no poseen orientación, representadas como conjuntos no ordenados \( \{u,v\} \).

---

### 2.4 Camino entre dos vértices
Un **camino** es una secuencia de vértices \( (v_0, v_1, ..., v_k) \) tal que cada par consecutivo \( (v_i, v_{i+1}) \) está conectado por una arista en \( E \).  
Un **camino simple** no repite vértices.

---

### 2.5 Árboles
Un **árbol** es un grafo no dirigido, conexo y acíclico que cumple:
- Posee \( n \) vértices y \( n-1 \) aristas.
- Existe un único camino simple entre cualquier par de vértices.

---

### 2.6 Grafos ponderados
Un **grafo ponderado** es aquel en el que cada arista \( e \in E \) posee un peso o costo asociado, definido mediante una función:

\[
w: E \rightarrow \mathbb{R}
\]

Estos grafos se utilizan para modelar redes de transporte, comunicación, costos, etc.

---

### 2.7 Vértices adyacentes y matriz de adyacencia
- Dos vértices \( u \) y \( v \) son **adyacentes** si existe una arista \( (u,v) \in E \).
- La **matriz de adyacencia** \( A \) de un grafo con \( n \) vértices es una matriz cuadrada \( n \times n \) tal que:

\[
A_{ij} =
\begin{cases}
1 & \text{si existe una arista entre } v_i \text{ y } v_j \text{ (o su peso en grafos ponderados)} \\
0 & \text{en caso contrario.}
\end{cases}
\]


