# PCB (_process control block_)

![[Pasted image 20211009190241.png]]
![[Pasted image 20211009190705.png]]

Cada proceso tiene su pcb, con los datos se gestiona la planificación.

El so debe tener acceso a todos los pc.

Cuando el proceso termina se libera la info de su pcb. 

Se guarda en el stack

Solo guarda info, no ejecuta nada.

Todas las pcb que estan en estado listo + tcb se guradan en la cola ready, y de ahi el itinerador saca la direcion y la escribe en el registro [[PC]] y ahi inicia la ejecucion de la tarea. 