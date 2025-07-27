# Semana 3

# Estrategia de Divide y Vencerás

## 1. Definición
La técnica de **Divide y Vencerás (Divide and Conquer)** es un paradigma de diseño de algoritmos que consiste en:
1. **Dividir** el problema en subproblemas de menor tamaño.
2. **Resolver recursivamente** cada subproblema.
3. **Combinar** las soluciones de los subproblemas para obtener la solución final.

Se utiliza cuando un problema puede descomponerse en instancias más pequeñas del mismo tipo, y su solución global se obtiene a partir de las soluciones parciales.

---

## 2. Ejemplos de Algoritmos con y sin Divide y Vencerás

### 2.1 Ejemplo sin optimización
**Búsqueda lineal en un arreglo ordenado:**

```python
def busqueda_lineal(arr, x):
    for i in range(len(arr)):
        if arr[i] == x:
            return i
    return -1

def busqueda_binaria(arr, x, izquierda, derecha):
    if izquierda > derecha:
        return -1
    medio = (izquierda + derecha) // 2
    if arr[medio] == x:
        return medio
    elif arr[medio] > x:
        return busqueda_binaria(arr, x, izquierda, medio-1)
    else:
        return busqueda_binaria(arr, x, medio+1, derecha)
def merge_sort(arr):
    if len(arr) <= 1:
        return arr
    medio = len(arr) // 2
    izquierda = merge_sort(arr[:medio])
    derecha = merge_sort(arr[medio:])
    return merge(izquierda, derecha)

def merge(izq, der):
    resultado = []
    i = j = 0
    while i < len(izq) and j < len(der):
        if izq[i] < der[j]:
            resultado.append(izq[i])
            i += 1
        else:
            resultado.append(der[j])
            j += 1
    resultado += izq[i:]
    resultado += der[j:]
    return resultado

