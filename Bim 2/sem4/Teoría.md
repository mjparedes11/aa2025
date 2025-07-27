#Semana 4

# Representaciones de Grafos: Lista Dinámica y Matriz de Adyacencia

## 1. Lista Dinámica (Lista de Adyacencia)

### 1.1 Definición
La **lista de adyacencia** es una estructura de datos utilizada para representar un grafo.  
Para cada vértice \( v \in V \), se almacena una **lista dinámica** que contiene todos los vértices adyacentes a \( v \).

### 1.2 Características
- Es eficiente en **espacio** para grafos dispersos (cuando \( |E| \ll |V|^2 \)).
- Permite **recorrer los vecinos de un vértice en tiempo proporcional a su grado**.

### 1.3 Ejemplo

Grafo no dirigido:



### 1.4 Complejidad
| Operación                      | Complejidad |
|--------------------------------|-------------|
| Obtener vértices adyacentes a v| \(O(\text{grado}(v))\) |
| Comprobar existencia de arista (u,v) | \(O(\text{grado}(u))\) |
| Espacio requerido              | \(O(|V| + |E|)\) |

---

## 2. Matriz de Adyacencia

### 2.1 Definición
La **matriz de adyacencia** de un grafo \( G = (V, E) \) con \( n = |V| \) vértices es una **matriz cuadrada** \( A \) de dimensión \( n \times n \) donde:

\[
A_{ij} =
\begin{cases}
1 & \text{si existe arista entre } v_i \text{ y } v_j \\
0 & \text{en caso contrario.}
\end{cases}
\]

En **grafos ponderados**, \( A_{ij} \) almacena el **peso de la arista**.

### 2.2 Ejemplo

Para el mismo grafo anterior con vértices \( V = \{A,B,C,D\} \):

|   | A | B | C | D |
|---|---|---|---|---|
| A | 0 | 1 | 1 | 0 |
| B | 1 | 0 | 0 | 1 |
| C | 1 | 0 | 0 | 1 |
| D | 0 | 1 | 1 | 0 |

### 2.3 Complejidad
| Operación                      | Complejidad |
|--------------------------------|-------------|
| Comprobar existencia de arista (u,v) | \(O(1)\) |
| Obtener vértices adyacentes a v| \(O(|V|)\) |
| Espacio requerido              | \(O(|V|^2)\) |

---

## 3. Comparación entre Representaciones

| Característica               | Lista de Adyacencia      | Matriz de Adyacencia   |
|------------------------------|-------------------------|------------------------|
| **Espacio requerido**        | \(O(|V|+|E|)\)         | \(O(|V|^2)\)          |
| **Verificar arista (u,v)**   | \(O(\text{grado}(u))\) | \(O(1)\)              |
| **Iterar sobre vecinos de v**| \(O(\text{grado}(v))\) | \(O(|V|)\)            |
| **Adecuado para**            | Grafos dispersos       | Grafos densos         |

---

## 4. Referencias
- Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2009). *Introduction to Algorithms*. MIT Press.
- Gross, J. L., & Yellen, J. (2006). *Graph Theory and Its Applications*. CRC Press.
