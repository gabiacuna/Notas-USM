### Tipos de Gráficos:
* ~~Torta~~
* ==Barras / Bar Chart== (Si se ordena de mayor a menor segun frecuencia se dice criterio pareto) 
* Tabligrama o Diagrama ==Tallo-Hoja / Steam and leaf== (Tabla de dos columnas, donde en la primera se encuentran todos los digitos de un numero y en la segunda solo el último de cada uno de los digitos que inicien iguales) , forma mas compacta de escribir datos.
* ==Diagramas de Puntos / Dot Plots== (Se pone un punto sobre una recta cada vez que aparece un dato)
---
### Histogramas
>Representacion simplificada/resumida de la distribución de frecuencias. (pero informa sobre la frecuencia acumulada o relativa de cada clase, que es una agrupacion de valores cercanos)

#### Construccion de un histograma :
Dado un valor de $K$,sea  
*  $x_{max} = max(x_1,x_2, . . . ,x_n)$  
* $x_{min} = min(x_1,x_2, . . . ,x_n)$  

> K nos dice cuantas columnas habrá en el histograma


Calculamos:
* **Rango**: $R=x_{max}−x_{min}$.
* **Amplitud**:$A = R/K.$
  * Reglas para determinar $K$.  
  \- Sturges: $K = \lceil log_2(n)\rceil + 1$  
  \- Raiz cuadrada : $K = \lceil \sqrt{n}\rceil$  
  \- Freedman-Diaconis: $A = 2 · IQR · n^{-1/3}$  
* La primera clase de valores $C_1$ se define como el intervalo $[x_{min},x_{min}+A]$.
* La clase $i$, con $i>1$, se define como el intervalo $(x_{min}+ (i−1)·A,x_{min}+i·A]$.

_Variantes_: holguras (caso entero), intervalos de la forma [a,b) y clases noequi-espaciadas.

---

Ejemplo:
Construya un histograma para los siguientes datos (use $K= 7$):

| 10 | 7 | 8 |   |   |   |   |   |   |   |
|----|---|---|---|---|---|---|---|---|---|
| 11 | 1 | 2 | 3 | 7 | 9 |   |   |   |   |
| 12 | 0 | 3 | 3 | 4 | 6 | 8 |   |   |   |
| 13 | 1 | 2 | 2 | 4 | 5 | 6 | 7 | 8 |   |
| 14 | 0 | 1 | 2 | 3 | 3 | 5 | 7 | 8 | 8 |
| 15 | 0 | 2 | 3 | 3 | 8 | 8 |   |   |   |
| 16 | 0 | 0 | 1 | 3 |   |   |   |   |   |
**Es un grafico de tallo y hoja, no se como hacerlo en md :c**
Estos pueden representar cualquier cosa, mientras se entrege la simbologia adecuada.
ej:
\- 13|1 = 0,131
\- 1|2 = 1200

[Dropbox con contenidos de la unidad](https://www.dropbox.com/sh/7p5z4i41cx25gvk/AACh8l41YBsUbUZ8WMhNZoFJa?dl=0)

_Video 3_:
[[Tema 1 - Medidas de Tendencia y Dispersion]]

[[estaca]]