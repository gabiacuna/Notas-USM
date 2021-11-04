Similar a la PCB para los procesos, la TCB, es una estructura de datos que guarda:
* Estado de la computación.
* Metadata de la hebra.

Guarda los datos del conexto de la hebra.

> Esta en el **kernel**!!!

![[Pasted image 20211103223704.png]]

Las hebras que son del mismo proceso, comparten info de este. Pero de todas formas cada una es independiente y tiene su propio entorno de ejecución.

Cada hebra tiene dos elementos de estados que la determinan:

![[Pasted image 20211103223849.png]]

Tenderemos prioridades por tipos de hebras.