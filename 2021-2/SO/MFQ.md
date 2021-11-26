# Multi Level Feedback Queue

Son una extención de Round Robin. Un RR con un quantum pequeño nos permite bajar el tiempo de respuesta de las tareas.

- implementar varias colas con algoritmos distintos
- Es __apropiativa__!
- Si un proceso termina antes de que se acabe el q y se pone a hacer E/S no se va a cambiar de cola????

![[Pasted image 20211115172914.png]]

A medida que se avanza en la cola, aumenta el quantum para que se puedan ejecutar correctamente las tareas.

![[Pasted image 20211115173005.png]]

Avanzan a medida que no van terminando.

## Ejemplo

![[Pasted image 20211115173205.png]]

Diagramar la plani y calcular los tiempos.

plani:
![[Pasted image 20211115175533.png]]

![[Pasted image 20211115175908.png]]