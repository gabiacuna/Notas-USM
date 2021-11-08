# Definición

![[Pasted image 20211008174809.png]]

![[Pasted image 20211008174857.png]]

![[Pasted image 20211008175522.png]]

El ejecutable tiene las instrucciones y los datos. Todos tienen la misma estructura pero con diferentes tamaños. 

> ![[Pasted image 20211008175704.png]]


![[Pasted image 20211008180122.png]]

![[Pasted image 20211008180303.png]]

El stack permite sacar una foto del proceso en el momento en el que se interrumpe.

![[Pasted image 20211008180529.png]]

El heap se usa super poquito.

![[Pasted image 20211008180603.png]]
![[Pasted image 20211009184355.png]]

Separamos la informacion relacionada a los procesos, 
1. los datos o la info del mismo proceso, que estan relacionados con su ejecución. (almacenados en la cajita 4 bloques)
2. Info de gestión del proceso , contexto de la ejecución del proceso.

## Comportamiento desde que es creado hasta que termina :3

![[Pasted image 20211009184838.png ]]

- nuevo : crear el proceso, si no hay errores, queda en estado listo.
- listo : Una vez que stan listos, pueden ser asignados a usar las cpu
- despachado : Cuando al evento se le asigna cpu
- Finalizado : Se ejecuta la ultima instrucción

> es muy probable que un proceso se vea interrumpido. Por lo que no llega directamente a la finalización

Ambos eventos producen una inteupcion , y se diferencian en que estado dejan al proceso. 

Por eventos de error, puede ser que un proceso se salte algun estado (abortar proceso)

El obj del diagrama de estados es gestionar estados.

-> [[PCB]] (_process control block_)