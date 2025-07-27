## Análisis de complejidad y relaciones de pertenencia Big-O

### Primer caso:
Sean:

- \( f(n) = n^3 + 9n^2 \log(n) \)
- \( g(n) = n^2 \log(n) \)

#### 1. Comprobar si \( f(n) \in O(g(n)) \)

Analicemos el comportamiento asintótico de \( f(n) \):

\[
f(n) = n^3 + 9n^2 \log(n)
\]

El término dominante es \( n^3 \), mientras que \( g(n) = n^2 \log(n) \), que crece más lentamente.

Entonces:

\[
\lim_{n \to \infty} \frac{f(n)}{g(n)} = \lim_{n \to \infty} \frac{n^3 + 9n^2 \log(n)}{n^2 \log(n)} = 
\lim_{n \to \infty} \left( \frac{n^3}{n^2 \log(n)} + \frac{9n^2 \log(n)}{n^2 \log(n)} \right) =
\lim_{n \to \infty} \left( \frac{n}{\log(n)} + 9 \right) = \infty
\]

Como el límite tiende a infinito, **\( f(n) \notin O(g(n)) \)**.

#### 2. Comprobar si \( f(n) \notin O(n^2) \)

\[
\lim_{n \to \infty} \frac{f(n)}{n^2} = \lim_{n \to \infty} \frac{n^3 + 9n^2 \log(n)}{n^2} = 
\lim_{n \to \infty} \left( n + 9 \log(n) \right) = \infty
\]

Entonces, **\( f(n) \notin O(n^2) \)**.

---

### Segundo caso:
Sean:

- \( f(n) = 2^n \)
- \( g(n) = 2^{2n} = (2^n)^2 = 4^n \)

#### 1. ¿\( f(n) \in O(g(n)) \)?

\[
\lim_{n \to \infty} \frac{f(n)}{g(n)} = \lim_{n \to \infty} \frac{2^n}{4^n} = \lim_{n \to \infty} \left( \frac{2}{4} \right)^n = \lim_{n \to \infty} \left( \frac{1}{2} \right)^n = 0
\]

Como el límite tiende a 0, entonces **\( f(n) \in O(g(n)) \)**.

#### 2. ¿\( g(n) \in O(f(n)) \)?

\[
\lim_{n \to \infty} \frac{g(n)}{f(n)} = \lim_{n \to \infty} \frac{4^n}{2^n} = \lim_{n \to \infty} 2^n = \infty
\]

Entonces, **\( g(n) \notin O(f(n)) \)**.

---

### Conclusión:

- \( f(n) = n^3 + 9n^2 \log(n) \notin O(n^2 \log(n)) \)
- \( f(n) \notin O(n^2) \)
- \( 2^n \in O(4^n) \)
- \( 4^n \notin O(2^n) \)
