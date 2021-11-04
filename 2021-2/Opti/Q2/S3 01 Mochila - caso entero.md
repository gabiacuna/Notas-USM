# [[Qin2]] - P1

![[Pasted image 20210920111137.png]]
 ![[Pasted image 20210920110831.png]]
 
 Utilizaremos una variable que nos diga cuantos objetos de cada tipo se deben incluir en la mochila
 La restriccion es no exeder la capacidad de la mochila
 La FO segun la cantidad max de articulos cargados en la mochila sería,
 
 $$max\ z = \sum x_i$$
 Con i el objeto del 1 al 5.
 $$max\ z = x_1 + x_2 + x_3 + x_4 + x_5$$
 
 Y las restricciones segun el peso de la mochila serían:
 
 $$12x_1 + 1x_2 + 4x_3 + 1x_4 + 2x_5 \leq 15$$
 
 Los valores posibles para las variables serían:
 
 >$$x_i \geq 0 \ \  \forall i = 1,...,n $$
  >$$x_i \in \mathbb{Z} \ \  \forall i = 1,...,n $$
  > Ahora $x_i$ pertenece a **enteros**, no reales.
 
 
 