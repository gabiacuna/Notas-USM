# Virtualización
![[Pasted image 20211008150153.png]]

Se puede levantar otro SO dento de un So, al que llamamos host. De forma  concurrente o paralela, dependiendo de la arquitectura.
![[Pasted image 20211008150505.png]]
Que es lo que tiene que hacer una gestionadora de maquinas virtuales(VMM) para lograr lo que queremos? -> lograr el efecto de que un so esta instalado dentro de un compu real.

En teoria se pueden tener más de una maquina en paralelo, se tienen distinros kernel, en el mismo hardware, por lo que la gestionadora se lleva la mayor carga.

## Tipos de implementación de VMM
![[Pasted image 20211008165917.png]]
Tipo 0 es standard, es casi una implementacion al nivel del compu. ya no se ocupa mucho.


![[Pasted image 20211008170218.png]]

Tiene que simular todo lo visto previamente en el capitulo (casi todo esta relacionado con las interrupciones). Estos So no se relacionan directamente con el hw, pero **no lo saben**. El unico que se comunica directamente con el hw es el so host.

Funca como un mapeador para los eventos y gestion de interrupciones.

La respuesta de la VMM depende de como el host gestiona los recursos y de como el guest cree que los esta gestionando.

![[Pasted image 20211008170226.png]]

El so esta utilizando el disco del compu. Pero es un disco virtual. (manejado por la VMM).
El inicio es darle play. 

![[Pasted image 20211008170831.png]]

La cpu esta ejecutando las instrucciones del so visita.

> Ambos modos se ejecutan en modo unsuario del host, aun que en si mismos el kernel piensa que es kernel.

![[Pasted image 20211008171859.png]]

la vmm se transforma en la herramienta gestora de interrupciones para el so guest. (como su vector de interrupciones). Si se requiere ejecutar una instruccion de tipo SO, puede ser que sea necesario cambiar de modo en el host.

![[Pasted image 20211008172301.png]]

* Trap son las interrupciones generadas por el so. 
* La VMM responde como si fuera el hw para el so guest.

![[Pasted image 20211008173527.png]]

-> La proteccion es un minimo!!!!!