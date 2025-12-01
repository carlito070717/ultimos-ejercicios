# Soluciones detalladas — Sistemas de Ecuaciones

Este README contiene la resolución paso a paso (con matrices en cada paso) de los ejercicios mostrados en la imagen, lista para usar en tu proyecto.

---

## Ejercicio 1

Sistema:

$$
\begin{cases}
x+y+z=6\
2x-y+z=3\
x+2y-z=2
\end{cases}
$$

Matriz de coeficientes y vector independiente:

$$
A=\begin{pmatrix}1&1&1\2&-1&1\1&2&-1\end{pmatrix},\quad
\mathbf b=\begin{pmatrix}6\3\2\end{pmatrix}.
$$

El sistema tiene determinante $\det(A)=7\neq0$, por tanto solución única. La solución final es $\boxed{(x,y,z)=(1,2,3)}$.

### a) Método de Gauss (eliminación y sustitución regresiva)

Matriz aumentada inicial:

$$
[ A\mid\mathbf b ] = \left[\begin{array}{ccc|c}
1 & 1 & 1 & 6\
2 & -1 & 1 & 3\
1 & 2 & -1 & 2
\end{array}\right]
$$

**Paso 1 — eliminar debajo del pivote (fila 1):**

Operaciones:

* $R_2 \leftarrow R_2 - 2R_1$.
* $R_3 \leftarrow R_3 - R_1$.

Resultado:

$$
\left[\begin{array}{ccc|c}
1 & 1 & 1 & 6\
0 & -3 & -1 & -9\
0 & 1 & -2 & -4
\end{array}\right]
$$

**Paso 2 — eliminar debajo del pivote (fila 2):**

Operación:

* $R_3 \leftarrow R_3 + \tfrac{1}{3}R_2$ (porque $R_2$ tiene $-3$ en la columna 2).

Cálculo explícito: $R_3 + \tfrac{1}{3}R_2 = [0,1,-2,-4] + \tfrac{1}{3}[0,-3,-1,-9] = [0,0,-7/3,-7]$.

Matriz triangular superior:

$$
\left[\begin{array}{ccc|c}
1 & 1 & 1 & 6\
0 & -3 & -1 & -9\
0 & 0 & -\tfrac{7}{3} & -7
\end{array}\right]
$$

**Sustitución regresiva:**

* Última fila: $-\tfrac{7}{3}z=-7 \Rightarrow z=3$.
* Segunda fila: $-3y - z = -9 \Rightarrow -3y - 3 = -9 \Rightarrow y=2$.
* Primera fila: $x+y+z=6 \Rightarrow x+2+3=6 \Rightarrow x=1$.

Solución: $\boxed{(1,2,3)}$.

---

### b) Método Gauss–Jordan (reducción completa)

Iniciando con la misma aumentada y aplicando operaciones hasta la forma reducida por filas (RREF), se llega al estado:

$$
\left[\begin{array}{ccc|c}
1&0&0&1\
0&1&0&2\
0&0&1&3
\end{array}\right]
$$

De lectura directa: $x=1,\ y=2,\ z=3$.

---

### c) Método de la matriz inversa

Si $A$ es invertible, $\mathbf x = A^{-1}\mathbf b$.

Cálculo de $A^{-1}$ (adjunta/determinante o mediante Gauss-Jordan para $[A|I]$):

$$
A^{-1}=\frac{1}{7}\begin{pmatrix}-1&3&2\3&-2&1\5&-1&-3\end{pmatrix}.
$$

Multiplicando:

$$
\mathbf x = A^{-1}\mathbf b = \begin{pmatrix}1\2\3\end{pmatrix}.
$$

---

### d) Regla de Cramer

Determinante $D=\det(A)=7$.

Matrices con la columna de términos independientes sustituyendo la columna correspondiente:

$$
A_x=\begin{pmatrix}6&1&1\3&-1&1\2&2&-1\end{pmatrix},\quad
A_y=\begin{pmatrix}1&6&1\2&3&1\1&2&-1\end{pmatrix},\quad
A_z=\begin{pmatrix}1&1&6\2&-1&3\1&2&2\end{pmatrix}.
$$

Determinantes: $\det(A_x)=7,\ \det(A_y)=14,\ \det(A_z)=21$.

Por Cramer:

$$
x=\frac{\det(A_x)}{D}=1,\quad y=2,\quad z=3.
$$

---

## Ejercicio 2 — Identificar tipo de solución

**a)**
$$\begin{cases}x+y=3\2x+2y=6\end{cases}$$
La segunda ecuación es múltiplo de la primera (dependientes) ⇒ **infinitas soluciones** (recta $x+y=3$).

**b)**
$$\begin{cases}x+y=3\2x+2y=7\end{cases}$$
La segunda no es múltiplo consistente de la primera ⇒ rectas paralelas incompatibles ⇒ **ninguna solución**.

**c)**
$$\begin{cases}x+y=3\x-y=1\end{cases}$$
Sumando: $2x=4\Rightarrow x=2$. Luego $y=1$. ⇒ **solución única** $(2,1)$.

---

## Ejercicio 3 — Sistema 4×4 (método más eficiente: eliminación de Gauss)

Sistema:

$$
\begin{cases}
x+y+z+w=10\
2x+y-z+w=5\
x-y+z-w=1\
x+y-z+2w=8
\end{cases}
$$

Matriz aumentada inicial:

$$
\left[\begin{array}{cccc|c}
1&1&1&1&10\
2&1&-1&1&5\
1&-1&1&-1&1\
1&1&-1&2&8
\end{array}\right]
$$

**Paso A — eliminar debajo de $R_1$:**

* $R_2\leftarrow R_2-2R_1$.
* $R_3\leftarrow R_3-R_1$.
* $R_4\leftarrow R_4-R_1$.

Resultado:

$$
\left[\begin{array}{cccc|c}
1&1&1&1&10\
0&-1&-3&-1&-15\
0&-2&0&-2&-9\
0&0&-2&1&-2
\end{array}\right]
$$

**Paso B — usar $R_2$ para eliminar $R_3$ en la columna 2:**

* Factor: $(-2)/(-1)=2$ → $R_3\leftarrow R_3 - 2R_2$.

Se obtiene:

$$
\left[\begin{array}{cccc|c}
1&1&1&1&10\
0&-1&-3&-1&-15\
0&0&6&0&21\
0&0&-2&1&-2
\end{array}\right]
$$

**Paso C — usar $R_3$ para eliminar $R_4$ (columna 3):**

* Factor: $(-2)/6 = -1/3$. Hacemos $R_4 \leftarrow R_4 + \tfrac{1}{3}R_3$.

Triangular superior final:

$$
\left[\begin{array}{cccc|c}
1&1&1&1&10\
0&-1&-3&-1&-15\
0&0&6&0&21\
0&0&0&1&5
\end{array}\right]
$$

**Sustitución regresiva:**

* $w=5$.
* $6z=21\Rightarrow z=7/2$.
* Segunda fila: $-y -3z - w = -15$. Sustituyendo $z=7/2, w=5$:
  [-0.5em]
  $-y - 3(7/2) -5 = -15 \Rightarrow -y - 21/2 -5 = -15$. Resolviendo: $y = -1/2$.
* Primera fila: $x + y + z + w = 10$. Sustituyendo $y,z,w$: $x - 1/2 + 7/2 +5 =10 \Rightarrow x=2$.

Solución:

$$
\boxed{(x,y,z,w) = \left(2, -\tfrac{1}{2}, \tfrac{7}{2}, 5\right)}
$$

(La matriz tiene determinante distinto de cero → solución única.)

---

## Ejercicio 4 — Aplicación práctica (producción)

Tres productos: Premium ($P$), Standard ($S$), Utilitario ($U$).

Consumo por unidad (kg):

* Premium: 2 res, 3 pollo, 1 cerdo.
* Standard: 1 res, 1 pollo, 2 cerdo.
* Utilitario: 3 res, 2 pollo, 1 cerdo.

Disponibles: res = 100 kg; pollo = 120 kg; cerdo = 80 kg.

Sistema:

$$
\begin{cases}
2P + 1S + 3U = 100 \
3P + 1S + 2U = 120 \
1P + 2S + 1U = 80
\end{cases}
$$

Matriz aumentada:

$$
\left[\begin{array}{ccc|c}
2&1&3&100\
3&1&2&120\
1&2&1&80
\end{array}\right]
$$

Determinante de la matriz de coeficientes: $8\neq0$ → solución única.

Resolución (mediante eliminación o $A^{-1}\mathbf b$) da:

$$
\begin{pmatrix}P\S\U\end{pmatrix}=\begin{pmatrix}55/2\45/2\15/2\end{pmatrix}=\left(27.5,;22.5,;7.5\right).
$$

**Interpretación:** con los recursos disponibles se obtienen $P=27.5$, $S=22.5$, $U=7.5$ unidades.

> **Nota:** Si las unidades deben ser enteras, hay que redondear o ajustar lotes; la solución real entera dependerá de la política de producción (p.ej. fabricar solo unidades completas y luego calcular sobrantes o faltantes).

---

## Observaciones finales

* Todas las matrices y pasos relevantes están incluidos arriba.
* Si quieres el mismo contenido convertido a un archivo `README.md` descargable o exportado en otro formato (por ejemplo `README.pdf`), dime y lo genero.
* Si quieres que los cálculos intermedios se muestren con entrada aritmética más detallada o quieres que convierta las fracciones a decimales en todos los pasos, lo actualizo.

---

*Hecho para: Carlos Alfonso Llanes*
