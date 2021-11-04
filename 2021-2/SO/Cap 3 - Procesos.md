# Cap3  Procesos
[ppt](https://aula.usm.cl/mod/resource/view.php?id=2500726)
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


# Itineración

![[Pasted image 20211009191851.png]]

No es lo mismo tener un proceso que este usando el 100% de la cpu, a tener 10 procesos y que el uso de la cpu 98%. Es mejor tener 10 procesos en forma concurrente, igual depende de más cosas. 
![[Pasted image 20211009191900.png]]


![[Pasted image 20211009192208.png]] 

- ![[Pasted image 20211011202246.png]]

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


# Operaciones
![[Pasted image 20211012003949.png]]

Para poder crear procesos utilizamos llamadas a sistema, que dependen de como las implementa cada so. 

![[Pasted image 20211012004045.png]]

Se tiene una jerarquia de procesos:
![[Pasted image 20211012004301.png]]

## Aristas de relaciones entre padre e hijo:
![[Pasted image 20211012004344.png]]

![[Pasted image 20211013171642.png]]
El kernel mencionado hace referencia a 2 ideas:
1. Memoria baja de la ram donde esta el SO ![[Pasted image 20211013171755.png]]
2. ????

![[Pasted image 20211013171901.png]]

## Llamadas al sistema en Unix
![[Pasted image 20211013171926.png]]
[[wait]] se usa para procesos que estan en una jerarquia.

![[Pasted image 20211013172109.png]]
En unix los padres tienen que esperar a sus hijos.

### [[Fork]]
![[Pasted image 20211013172122.png]]

Esto es lo que hace  la shell:
![[Pasted image 20211013172132.png]]

#### Ejemplo
![[Pasted image 20211013172327.png]]
pid es un nombre de variable, esta es de tipo entero

El proceso hijo no sabe cual es su Id, pero para obtenerlo `getpid()`.

![[Pasted image 20211013173224.png]]

![[Pasted image 20211013173236.png]]

Crear el nuevo espacio depende de la gestion de la memoria principal (GMP).

El itinerador esta al tanto ya que esta al tanto de la cola ready, y el proceso nuevo, si no hay un error, queda ahí.

![[Pasted image 20211013173413.png]]

Si meto un nuevo programa, este parte desde el inicio y el espacio se ajusta segun las necesidades.

## Cración / Ejemplos

![[Pasted image 20211013173708.png]]
![[Pasted image 20211013173727.png]]
wait null hace que espere a los hijos 
**ej 2 tareita**
![[Pasted image 20211013180331.png]]
## Otras operaciones
![[Pasted image 20211013180741.png]]
![[Pasted image 20211013180751.png]]

# Comunicación

Permite que los procesos se comuniquen entre si. Pueden  compartir un objetivo en comun pero no modificarlos.

Debería existir una forma de compartir una variable.

![[Pasted image 20211025171805.png]]

![[Pasted image 20211025171914.png]]

Para la memoria compartida:

![[Pasted image 20211025172244.png]]

P0 puede direccionar a la region azul y a la region de P0.

![[Pasted image 20211025172552.png]]

Los procesos deben estar sincronizados.

![[Pasted image 20211025172622.png]]

## Por [[Paso de Mensajes]]

#SO 