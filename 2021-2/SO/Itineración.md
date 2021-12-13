# Itineración

![[Pasted image 20211009191851.png]]

No es lo mismo tener un proceso que este usando el 100% de la cpu, a tener 10 procesos y que el uso de la cpu 98%. Es mejor tener 10 procesos en forma concurrente, igual depende de más cosas. 
![[Pasted image 20211009191900.png]]


![[Pasted image 20211009192208.png]] 

- ![[Pasted image 20211011202246.png]]

## itineradores

![[Pasted image 20211011202426.png]]
MP : Memoria principal -> RAM
Tambien puede haber un itinerador a mediano plazo. 

> ## Cual de los dos controla el grado de multiprogramación?
> Mientras mas procesos se tienen con un alto grado de cpu, mayor es el grado de multiprogramación. 
> Es el itinerador a largo plazo, ya que es el que lleva la carga a la memoria principal. Para poder ejecutar más procesos tengo que tenerlos en la RAM.
> El de corto plazo no puede hacer nada si la ram está vacia.

Ambos deben tomar deciciones inteligentes para no pegarle al desempeño.

![[Pasted image 20211011202515.png]]

Lo ideal sería que el itinerador de largo plazo pueda hacer un mix, así no existirian los casos bordes.

## Casos Borde:

![[Pasted image 20211011203336.png]]
Falta en el caso borde 2:
-	posible impacto a la multiprogramación
Se busca evitar que la CPU quede ociosa.

![[Pasted image 20211011204510.png]]

Existen tantas pcb como procesos existan en el sistema.

![[Pasted image 20211011204748.png]]