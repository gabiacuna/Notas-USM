## Medidas de Tendencia 

>Valor numerico que representa el conjunto de observaciones muestrales disponibles.

* ==Moda== : valor o clase de valores con mayor frecuencia.

* ==Media Muestral== $\bar{x}$: promedio aritmético de los valores en la muestra. -> muy sensible a valores extremos (_outliers_), cuando hay no prefleja la tendencia de la gran mayoría de observaciones. 
	* La media generalmente tiene un valor decimal extra que las observaciones (ej. las observaciones son 8 3 2, la mediana sería 4,3)

* ==Mediana Muestral== : estadistica de orden, que divide la muestra en dos grandes mitades $(- \infty , \tilde{x}]$ y $[\tilde{x}, \infty]$.
	* Calculo de la mediana:
	con $x_1 , x_2 ... x_n$	las observaciones ordenadas en forma creciente, 
	Si $n$ es impar, la mediana es:
		$\tilde{x} = x_{(\frac{n+1}{2}})$
	Si $n$ es par, 
		$\tilde{x} = \frac{x_{\frac{n-1}{2}} + x_{\frac{n+1}{2}}}{2}$
		
		\* ver ejemplo de claculo de la mediana! y buscar medias trucadas en el texto guía
	
	-> Super resistente a los outliers, no toma en cuenta la magnitud de las observaciones, excepto aquella que divide ela muestra en dos proporciones identicas. 

* ==Sesgo== : $\bar{x} - \tilde{x}$ (Asimetría, Skew)
	* Si sesgo = 0, la inclinacion del histograma esta en el centro.
	* Si sesgo $\leq$ 0, el sesgo está a la izquierda.
	* Si sesgo $\geq$ 0, el sesgo esta a la derecha.
	
-> La moda siempre estara en lo mas alto de la montaña, si hay una cola, la media se vera más afectada que la mediana. El sesgo nos muestra aprox donde estan la media y la mediana (a que lado de la montaña)


* ==Media Poblacional== $\mu$ : Si la población es finita se pueden medir todoslos valores de x en la población y luego clacular su promedio.
	* En lo gerenal difiere del promedio muestral $\bar{x}$.

## Medidas de disperción
>Valor numérico que mide el grado de concentracion de las observaciones en torno a un valor de tendencia.

* ==Rango== : max(S) - min(S) , S es el dataset-.
* ==Índice de Variación== : $1 - f_M$ con $f_m$ la frecuencia relativa de la moda.
* ==Variaza Muestral== $s^2$ o $\hat{s}^2$ : Mide la dispercion en torno al valor de tendencia que es la media.
	* Se calcula:
	$$s^2 = \frac{\sum_{i=1}^{n} (x_i - \bar{x})²}{n-1}$$
* ==Desviacion estándar muestral== $s$ o $\hat{\sigma}$ : Nos entrega una desviasión de los datos.
	* se clacula:
	$$s = \sqrt{s²} = \sqrt{\frac{\sum_{i=1}^{n} (x_i - \bar{x})²}{n-1}}$$
---
#### Rango Inter-Cuartílico IQR

Para medir **dispersión en torno a la mediana** (divide los datos en 50% 50%) ,  queremos:
- Medida ==basada en frecuencia== : La medicion de la mediana y su dispercion se definen en términos del histograma de frecuencias empíricas.
- ==Resistencia a outliers== : La mediana y su dispercion deberian ser resistentes a los outliers 

Definiremos los **cuartiles**, 1, 2y 3; Que son los valores que dividen el histograma de frecuencias en 4 partes de igual proporción.
 -> Cada cuartil contiene un 25% de los datos.
 -> Los conoceremos por $Q_1, Q_2$ y $Q_3$.
_Def formal en la diapo 95_
* Primero se define $Q_2$ que es la mediana de todo el conjunto.
* Luego calculamos la mediana de cada mitad, obteniendo $Q_1$ y $Q_3$.

_Resolver ejemplos diapo 96 en adelante_

> $$IQR = Q_3 - Q_1$$ Esta es la medida de dispersión de la mediana

---
Un **Boxplot** esta basado en los cuartiles:
\- Modo conveniente de mostrar la tendencia /dispersión de los datos (usando $Q_1$, $Q_2$ y $Q_3$).
![](boxplot_img.png)
Dentro de la caja se encuentran los valores dentro del rango $Q_1$ -$Q_2$ y $Q_2$ -$Q_3$. 
Fuera de esta estan los ==Bigotes== que representan el rango de las observaciones que noson atípicas o extremas (outliers).  Para encontrarlos se usa un rango de tolerancia $[L_{inf}, L_{sup}]$.  
 
$$L_{inf} = Q_1 - 1,5 · IQR$$
$$L_{sup} = Q_1 + 1,5 · IQR$$

El _bigote mayor_ es la obs. mas grande dentro del rango de tolerancia. Y el _bigote menor_ es la obs más pequeña. 

> Sirven para ver donde esta la mayor acumulacion de datos c:

[Dropbox con contenidos de la unidad](https://www.dropbox.com/sh/7p5z4i41cx25gvk/AACh8l41YBsUbUZ8WMhNZoFJa?dl=0)

[[estaca]]