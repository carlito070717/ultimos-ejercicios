# Soluciones — Sistemas y Aplicación Práctica

**Nombre:** Carlos Alfonso Llanes  
**Materia:** Fundamentos de Álgebra  
**Maestro:** Jorge Javier Pedrozo  
**Escuela:** Tecnológico de Software  
**Fecha:** 03/12/2025  

---

## Ejercicio 1 — Resolver con todos los métodos

Sistema:
\[
\begin{cases}
x + y + z = 6 \\
2x - y + z = 3 \\
x + 2y - z = 2
\end{cases}
\]

Representación matricial \(A\mathbf{x}=\mathbf{b}\):

$`\begin{bmatrix} 1 & 1 & 1 \\ 2 & -1 & 1 \\ 1 & 2 & -1 \end{bmatrix}`$
$`\begin{bmatrix} x \\ y \\ z \end{bmatrix}`$
=
$`\begin{bmatrix} 6 \\ 3 \\ 2 \end{bmatrix}`$

---

### **a) Método de Gauss**

Matriz aumentada inicial:

$`\left[\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
2 & -1 & 1 & 3 \\
1 & 2 & -1 & 2
\end{array}\right]`$

1. **Eliminar primera columna:**

- \(F_2 \leftarrow F_2 - 2F_1\)  
- \(F_3 \leftarrow F_3 - F_1\)

$`\left[\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
0 & -3 & -1 & -9 \\
0 & 1 & -2 & -4
\end{array}\right]`$

2. **Eliminar segundo pivote:**
~~\(F_2 \leftarrow F_2 + 3F_3\)

$`\left[\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
0 & 1 & -2 & -4 \\
0 & 0 & -7 & -21
\end{array}\right]`$

3. **Sustitución hacia atrás:**

- \(z = 3\)  
- \(y = 2\)  
- \(x = 1\)

✔ **Solución:**  
\[
(x,y,z) = (1,2,3)
\]

---

### **b) Método Gauss–Jordan**

Después de reducir completamente:

$`\left[\begin{array}{ccc|c}
1 & 0 & 0 & 1 \\
0 & 1 & 0 & 2 \\
0 & 0 & 1 & 3
\end{array}\right]`$

✔ **Solución:** \((1,2,3)\)

---

### **c) Método de la Matriz Inversa**

$A^{-1}=$
$`\begin{bmatrix}
-1/7 & 3/7 & 2/7 \\
 3/7 & -2/7 & 1/7 \\
 5/7 & -1/7 & -3/7
\end{bmatrix}`$

Multiplicando:

\[
A^{-1}b =
\begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}
\]

✔ **Solución:** \((1,2,3)\)

---

### **d) Regla de Cramer**

- \(\det(A)=7\)
- \(x = 1, \ y = 2, \ z = 3\)

✔ **Solución:** \((1,2,3)\)

---

## Ejercicio 2 — Identificar tipo de solución

### **a)**  
Ecuaciones dependientes → **infinitas soluciones**.

### **b)**  
Sistema incompatible → **ninguna solución**.

### **c)**  
Solución única:  
\[
(x,y) = (2,1)
\]

---

## Ejercicio 3 — Sistema 4×4

Sistema:
\[
x + y + z + w = 10 \\
2x + y - z + w = 5 \\
x - y + z - w = 1 \\
x + y - z + 2w = 8
\]

Matriz:

$`\begin{bmatrix}
1 & 1 & 1 & 1 \\
2 & 1 & -1 & 1 \\
1 & -1 & 1 & -1 \\
1 & 1 & -1 & 2
\end{bmatrix}`$

Determinante: \(-6\) → solución única.

✔ **Solución:**
\[
x = 2,\quad y = -\tfrac{1}{2},\quad z = \tfrac{7}{2},\quad w = 5
\]

---

## Ejercicio 4 — Aplicación práctica

Sistema:

\[
2P + S + 3U = 100 \\
3P + S + 2U = 120 \\
P + 2S + U = 80
\]

Matriz:

$`\begin{bmatrix}
2 & 1 & 3 \\
3 & 1 & 2 \\
1 & 2 & 1
\end{bmatrix}`$

Determinante: 8 → solución única.

✔ **Solución:**

\[
P = 27.5,\quad S = 22.5,\quad U = 7.5
\]

---

## Fin del documento.
