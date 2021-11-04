# [[Qin2]] - P2
Ahora solo tenemos uno de cada objeto. por lo que lo que antes era $x_i \in \mathbb{Z}$ ahora es $x_i \in \{0, 1\}$ :
$$
 x_i = \begin{cases} \mbox{0,} & \mbox{si } x_i \mbox{ no va en la mochila}\\ \mbox{1,} & \mbox{si } x_i \mbox{ va en la mochila} \end{cases} 
$$

Ahora solo queremos saber la menjor combinacion de objetos y maximizar la cantidad de objetos incluidos.

FO:
![[Pasted image 20210920112752.png]]
Restricciones: 
![[Pasted image 20210920112809.png]]

Ahora para el caso general, con n objetos, peso $v_i$, precio $u_i$ y capacidad maxima de la mochila V,

![[Pasted image 20210920113022.png]]

Si se quiere maximizar la utilidad:

![[Pasted image 20210920113256.png]]
