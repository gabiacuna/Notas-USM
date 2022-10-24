1. Como sincronizamos los relojes con los relojes del mundo real?
2. Como sincronizamos los relojes entre sí?

Con el paso de mensajes podemos sincronizar aproximadamente un reloj. Y usando un reloj lógico, podemos definir el orden de eventos sin medir el tiempo físico en el que ocurrieron.

Se tienen diferentes enfoques:

- Con UTC (*Coordinated Universal Time*): Cada nodo puede compartir su hora local con los nodos cercanos, y se mantienen sincronizados a una maquina con receptor UTC, utilizando NTP (*Network time protocol*). 
	↪ Obj: Mantener la desviación del reloj ligada a un valor $\alpha$ (exactitud / accuracy).
- Sin UTC : Se sincronizan las maquinas entre sí. 
	↪ Obj: Mantener la desviación entre los relojes ligada a un valor $\pi$ (precisión/precision).

> **Reloj de sw**: se deriva del reloj de hw del compu. 

⭐Ser exactos no nos permite concluir nada sobre la precisión de los relojes.

## Protocolo de tiempo de red (NTP)

Se tiene un servidor horario que tiene un reloj muy preciso. Este se disponibiliza en internet, pero la latencia de la red es muy variable.

|Se mide la latencia: <br> - $\theta$ : Compensación relativa a B. <br>- $\delta$ : Estimación de retraso <br> se calculan 8 pares ($\theta$, $\delta$) tomando el valor minimo encontrado para $\delta$ como la mejor estimacion de demora entre dos servidores  y el valor asociado a $\theta$ como la estimacion mas confiable de la compensación|![[Pasted image 20221023134305.png]]|
|-|-|

- NTP usa una capa de servidores de tiempo llamados **estratos**.
![[Pasted image 20221023135312.png]]
- Estrato 0, reloj de referencia atómico o GPS ($\pm 10$ ns).
- Estrato 1, Un servidor conectado al reloj del estrato 0 ($\pm 5$ $\micro$s).
- Estrato 2, servidores que se sincronizan con el estrato 1 ($\pm 10$ ms).

## Algoritmo de Berkeley

En este algoritmo el Time Server está activo.
- se sondea la maquina cada cierto tiempo para preguntar que hora es ahi.
- En base a las respuestas se calcula el tiempo promedio y se le dice a las otras maquinas que ajusten sus relojes a esa hora.
![[Pasted image 20221023135843.png]]
1. Daemon de tiempo pregunta todos los valores del reloj.
2. las maquinas responden.
3. el daemon del tiempo les dice a todos como ajustar su reloj.

Este algo ignora las lecturas de los relojes con sesgos demasiado grandes. Calcula un promedio tolerante a fallas y calcula el desplazamiento enviado a cada nodo.

|![[Pasted image 20221023164706.png]]|![[Pasted image 20221023164720.png]]|
|-|-|

