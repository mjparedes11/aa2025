# Semana 6

# Multiplicación de Matrices y Algoritmo de Strassen

## 1. Multiplicación de Matrices Convencional

### Definición
Dadas dos matrices \( A \) y \( B \) de dimensiones \( n \times n \), su producto \( C = A \cdot B \) se calcula como:

\[
C_{ij} = \sum_{k=1}^{n} A_{ik} \cdot B_{kj}
\]

### Algoritmo Clásico
```python
def multiplicacion_matrices(A, B):
    n = len(A)
    C = [[0] * n for _ in range(n)]
    for i in range(n):
        for j in range(n):
            for k in range(n):
                C[i][j] += A[i][k] * B[k][j]
    return C


def strassen(A, B):
    n = len(A)
    if n == 1:
        return [[A[0][0] * B[0][0]]]

    # Dividir matrices en submatrices
    mid = n // 2
    A11, A12, A21, A22 = dividir(A, mid)
    B11, B12, B21, B22 = dividir(B, mid)

    # Calcular las 7 multiplicaciones
    M1 = strassen(sumar(A11, A22), sumar(B11, B22))
    M2 = strassen(sumar(A21, A22), B11)
    M3 = strassen(A11, restar(B12, B22))
    M4 = strassen(A22, restar(B21, B11))
    M5 = strassen(sumar(A11, A12), B22)
    M6 = strassen(restar(A21, A11), sumar(B11, B12))
    M7 = strassen(restar(A12, A22), sumar(B21, B22))

    # Combinar resultados
    C11 = sumar(restar(sumar(M1, M4), M5), M7)
    C12 = sumar(M3, M5)
    C21 = sumar(M2, M4)
    C22 = sumar(restar(sumar(M1, M3), M2), M6)

    return combinar(C11, C12, C21, C22)

