# Shortest Job First

> Las tareas más cortas van al principio. El objetivo es reducir el uso de la cpu????? 

> La CPU se le asigna a la tarea más corta, prioriza los procesos que duran menos!!!

![[Pasted image 20211108180101.png]]

El so no sabe exactamente cuanto va a tomar un proceso. SJF solo se ocupa para comparar con otros algoritmos, para tenerlos como base. 

![[Pasted image 20211108180157.png]]


> ## [[Inanición]]
> Las tareas más cortas se ven favorecidas, por lo que una tarea larga se puede quedar en espera para siempre. Especialmente si es Apropiativo, ya que aun que se empiece a ejecutar, puede ser que no termine nunca.
> ![[Pasted image 20211108180552.png]]


La inanicion se combate con **envejecimiento**, se le sube la prioridad a un proceso que se esta demorando mucho mas de lo necesario. 

-> SJF vs [[FCFS]]

![[Pasted image 20211108180604.png]]

## Ej Cooperativo

![[Pasted image 20211108180615.png]]

| | Tiempo de Respuesta |
|---|---|
| **P1** | 0 |
| **P2** | 7 |
| **P3** | 9 |
| **P3** | 15 |

- P2 llegó en 1!!!

Aqui no hay interrupciones, entonces el $T_{esp}$\* es 0.

## Ej Apropiativo

![[Pasted image 20211108180629.png]]

| | Tiempo de Respuesta | Tiempo espera \* | Tiempo de Ejec |
|---|---|---|---|
| **P1** | 0 | 9 | 17 |
| **P2** | 0 | 0 | 4 |
| **P3** | 15 | 0 | 24 |
| **P3** | 2 | 0 | 7 |

Tiempo de espera \* es el tiempo que estubo un proceso detenido en la cola ready luedo se haber pasado por la cpu.