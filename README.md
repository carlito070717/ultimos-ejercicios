
# Soluciones — Sistemas y aplicación práctica

A continuación están las resoluciones y procedimientos solicitados. Donde corresponda, se usan **matrices** en el formato requerido: $`\begin{bmatrix} ... \end{bmatrix}`$

---

## Ejercicio 1 — Resolver con todos los métodos
Sistema:
\begin{align*}
x + y + z &= 6 \\
2x - y + z &= 3 \\
x + 2y - z &= 2
\end{align*}

Representación matricial $A\mathbf{x}=\mathbf{b}$:
$` \begin{bmatrix} 1 & 1 & 1 \\ 2 & -1 & 1 \\ 1 & 2 & -1 \end{bmatrix}`$ \quad
$` \begin{bmatrix} x \\ y \\ z \end{bmatrix}`$ = $` \begin{bmatrix} 6 \\ 3 \\ 2 \end{bmatrix}`$

### a) Método de Gauss (eliminación hacia adelante y sustitución)
Formamos la matriz aumentada:
$` \left[\begin{array}{ccc|c} 1 & 1 & 1 & 6 \\[2pt] 2 & -1 & 1 & 3 \\[2pt] 1 & 2 & -1 & 2 \end{array}\right]`$

1. Eliminar la primera columna debajo de la fila 1:
   - $F_2 \leftarrow F_2 - 2F_1$ → $[\,0,\ -3,\ -1\;|\; -9\,]$
   - $F_3 \leftarrow F_3 - F_1$ → $[\,0,\ 1,\ -2\;|\; -4\,]$

   Nueva aumentada:
   $` \left[\begin{array}{ccc|c} 1 & 1 & 1 & 6 \\[2pt] 0 & -3 & -1 & -9 \\[2pt] 0 & 1 & -2 & -4 \end{array}\right]`$

2. Hacer pivote en la fila 2 (columna 2): intercambiamos signos para comodidad o usamos combinación:
   - $F_2 \leftrightarrow F_3$ (opcional) o eliminar usando $F_2 \leftarrow F_2 + 3F_3$.
   Usaremos: $F_2 \leftarrow F_2 + 3F_3$:
   - $F_2$: $[0, -3, -1 | -9] + 3[0,1,-2|-4] = [0,0,-7|-21]$

   Matriz:
   $` \left[\begin{array}{ccc|c} 1 & 1 & 1 & 6 \\[2pt] 0 & 1 & -2 & -4 \\[2pt] 0 & 0 & -7 & -21 \end{array}\right]`$ 
   (Nota: la fila 2 y 3 reordenadas para claridad).

3. Sustitución hacia atrás:
   - De la última fila: $-7z = -21 \Rightarrow z = 3$.
   - Fila 2: $y - 2z = -4 \Rightarrow y - 2(3) = -4 \Rightarrow y - 6 = -4 \Rightarrow y = 2$.
   - Fila 1: $x + y + z = 6 \Rightarrow x + 2 + 3 = 6 \Rightarrow x = 1$.

**Solución:** $x=1,\ y=2,\ z=3$.

### b) Gauss–Jordan (reducción por filas hasta forma reducida)
Partimos de la matriz aumentada original y realizamos operaciones hasta tener la identidad a la izquierda.

Matriz aumentada inicial:
$` \left[\begin{array}{ccc|c} 1 & 1 & 1 & 6 \\ 2 & -1 & 1 & 3 \\ 1 & 2 & -1 & 2 \end{array}\right]`$

Operaciones resumidas (mostraré las operaciones clave y resultado final reducido):
- $F_2 \leftarrow F_2 - 2F_1$; $F_3 \leftarrow F_3 - F_1$ → como en Gauss.
- Normalizar y eliminar para conseguir la matriz identidad a la izquierda. Tras las operaciones obtenemos:
$` \left[\begin{array}{ccc|c} 1 & 0 & 0 & 1 \\ 0 & 1 & 0 & 2 \\ 0 & 0 & 1 & 3 \end{array}\right]`$

De donde se lee inmediatamente: $x=1,\ y=2,\ z=3$.

### c) Método de la matriz inversa
Si $A$ es la matriz de coeficientes, y $A$ es invertible, $\mathbf{x}=A^{-1}\mathbf{b}$.

$A = $ $` \begin{bmatrix} 1 & 1 & 1 \\ 2 & -1 & 1 \\ 1 & 2 & -1 \end{bmatrix}`$

Se calcula $A^{-1}$ (omitimos el desarrollo completo del cálculo de la adjunta para brevedad; se puede obtener por Gauss–Jordan sobre $[A|I]$). Resultado:
$` \begin{bmatrix} -\tfrac{1}{7} & \tfrac{3}{7} & \tfrac{2}{7} \\[2pt] \tfrac{3}{7} & -\tfrac{2}{7} & \tfrac{1}{7} \\[2pt] \tfrac{5}{7} & -\tfrac{1}{7} & -\tfrac{3}{7} \end{bmatrix}`$

Multiplicando $A^{-1}\mathbf{b}$:
$` \begin{bmatrix} -\tfrac{1}{7} & \tfrac{3}{7} & \tfrac{2}{7} \\ \tfrac{3}{7} & -\tfrac{2}{7} & \tfrac{1}{7} \\ \tfrac{5}{7} & -\tfrac{1}{7} & -\tfrac{3}{7} \end{bmatrix}`$ $` \begin{bmatrix} 6 \\ 3 \\ 2 \end{bmatrix}`$ = $` \begin{bmatrix} 1 \\ 2 \\ 3 \end{bmatrix}`$.

### d) Regla de Cramer
Sea $A$ y $b$ como antes. Determinante de $A$: $\det(A)=7$ (no nulo → solución única).

Formamos matrices $A_x,A_y,A_z$ reemplazando la columna correspondiente por $b$:
- $A_x = $ $` \begin{bmatrix} 6 & 1 & 1 \\ 3 & -1 & 1 \\ 2 & 2 & -1 \end{bmatrix}`$ → $\det(A_x)=7$ → $x=\det(A_x)/\det(A)=1$.
- $A_y = $ $` \begin{bmatrix} 1 & 6 & 1 \\ 2 & 3 & 1 \\ 1 & 2 & -1 \end{bmatrix}`$ → $\det(A_y)=14$ → $y=14/7=2$.
- $A_z = $ $` \begin{bmatrix} 1 & 1 & 6 \\ 2 & -1 & 3 \\ 1 & 2 & 2 \end{bmatrix}`$ → $\det(A_z)=21$ → $z=21/7=3$.

Confirma: $x=1,y=2,z=3$.

---

## Ejercicio 2 — Identificar tipo de solución
Para cada sistema determinamos si tiene solución única, infinitas o ninguna.

a) \(\begin{cases} x+y=3 \\ 2x+2y=6 \end{cases}\)

Multiplicando la primera ecuación por 2 se obtiene la segunda; las ecuaciones son dependientes → **infinitas soluciones** (dos ecuaciones equivalentes, 1 ecuación independiente con 2 incógnitas).

b) \(\begin{cases} x+y=3 \\ 2x+2y=7 \end{cases}\)

La segunda ecuación sería 2 veces la primera en la parte izquierda, pero las constantes no coinciden (6 ≠ 7) → **sistema incompatible, ninguna solución**.

c) \(\begin{cases} x+y=3 \\ x-y=1 \end{cases}\)

Sumando: \(2x=4 \Rightarrow x=2\). Luego \(y=1\). Ecuaciones independientes → **solución única**: \(x=2,\ y=1\).

---

## Ejercicio 3 — Sistema \(4\times 4\)
Sistema:
\begin{align*}
x + y + z + w &= 10 \\
2x + y - z + w &= 5 \\
x - y + z - w &= 1 \\
x + y - z + 2w &= 8
\end{align*}

Matriz de coeficientes y vector independiente:
$` \begin{bmatrix} 1 & 1 & 1 & 1 \\[2pt] 2 & 1 & -1 & 1 \\[2pt] 1 & -1 & 1 & -1 \\[2pt] 1 & 1 & -1 & 2 \end{bmatrix}`$ , \quad $` \begin{bmatrix} 10 \\ 5 \\ 1 \\ 8 \end{bmatrix}`$

Es eficiente usar eliminación de Gauss (o factorización LU). A continuación se muestra el resultado clave y la verificación por inversa:

Determinante de la matriz: $\det(A)=-6$ (distinto de 0 → solución única).

Resolviendo (por eliminación o inversa) se obtiene:
\[
x = 2,\quad y = -\tfrac{1}{2},\quad z = \tfrac{7}{2},\quad w = 5.
\]

Verificación rápida: sustituir en la primera ecuación:
\(2 + (-1/2) + 7/2 + 5 = 2 -0.5 +3.5 +5 =10\) ✔

También la matriz inversa (calculada por Gauss–Jordan sobre $[A|I]$) es:
$` \begin{bmatrix} 0 & \tfrac{1}{3} & \tfrac{1}{3} & 0 \\[2pt] \tfrac{1}{2} & \tfrac{2}{3} & -\tfrac{5}{6} & -1 \\[2pt] \tfrac{1}{2} & -\tfrac{1}{3} & \tfrac{1}{6} & 0 \\[2pt] 0 & -\tfrac{2}{3} & \tfrac{1}{3} & 1 \end{bmatrix}`$

y $\mathbf{x}=A^{-1}\mathbf{b}$ da el mismo resultado mostrado arriba.

---

## Ejercicio 4 — Aplicación práctica (producción)
La empresa produce tres productos: Premium (P), Standard (S) y Utilitario (U).
Recursos usados: res (R), pollo (Q), cerdo (C).
Consumos por unidad de producto:
- Premium: 2 kg res, 3 kg pollo, 1 kg cerdo.
- Standard: 1 kg res, 1 kg pollo, 2 kg cerdo.
- Utilitario: 3 kg res, 2 kg pollo, 1 kg cerdo.

Disponibles: 100 kg res, 120 kg pollo, 80 kg cerdo.

Planteamiento (variables: \(P,S,U\) = unidades a fabricar):
\begin{align*}
2P + 1S + 3U &= 100 \quad\text{(res)}\\
3P + 1S + 2U &= 120 \quad\text{(pollo)}\\
1P + 2S + 1U &= 80  \quad\text{(cerdo)}
\end{align*}

Matriz y vector:
$` \begin{bmatrix} 2 & 1 & 3 \\[2pt] 3 & 1 & 2 \\[2pt] 1 & 2 & 1 \end{bmatrix}`$ $` \begin{bmatrix} P \\ S \\ U \end{bmatrix}`$ = $` \begin{bmatrix} 100 \\ 120 \\ 80 \end{bmatrix}`$

Determinante: $\det=8 \neq 0$ → solución única (aunque no necesariamente entera). Resolviendo:
\[
P = \tfrac{55}{2} = 27.5,\quad S = \tfrac{45}{2} = 22.5,\quad U = \tfrac{15}{2} = 7.5.
\]

Interpretación: con las cantidades dadas se pueden fabricar en teoría 27.5 unidades Premium, 22.5 Standard y 7.5 Utilitario. Si se requieren **unidades enteras** será necesario redondear o plantear un problema de optimización entero (enteros) o ajustar mezcla de productos — el sistema lineal clásico da la solución real continua indicada.

---

### Observaciones finales
- Donde \(\det(A)\neq 0\) el sistema tiene solución única (puede hallarse por Gauss, Gauss–Jordan, inversa o Cramer).  
- Cuando las ecuaciones son proporcionales y el término independiente también lo es hay infinitas soluciones; si los términos independientes no siguen la proporcionalidad el sistema es incompatible (ninguna solución).

---
*Archivo generado automáticamente con los procedimientos solicitados.*
