# Planificación de uso de CPU

1. Conceptos Básicos
2. Algoritmos de Itineración
3. Multiprocesamiento

# Conceptos Básicos

Cuando hay muchas tareas por hacer, ¿Cuál ejecutamos primero?. El criterio de selección definirá la naturaleza del SO.

- Objetivo principal: _Maximizar_ el uso de la CPU.
- La idea es simple: Si la ejecución de un proceso es interrumpida (sin
importar la razón), otro debe tomar su lugar.
- Toda polı́tica de itineración presenta un complejo conjunto de
decisiones entre varias propiedades deseables.

El itinerador elige un proceso desde la cola ready y le asigna la CPU.
- Las decisiones de itineración se toman cuando los procesos pasan:
	- Desde el estado running a waiting.
	- Desde el estado running a ready.
	- Desde el estado waiting a ready.
	- Fin de un proceso.

El despachador entrega el control de la CPU al proceso seleccionado
por le itinerador de corto plazo.
- Esta asignación produce:
	- Cambio de contexto.
	- Cambio a modo usuario.
	- Saltar a la dirección correcta dentro del programa y reiniciarlo.
- El despachador debe ser lo más rápido posible.
- El tiempo que utiliza en detener un proceso e iniciar la ejecución de
otro se conoce como tiempo de latencia del despachador.

![[Pasted image 20211124131745.png]]

![[Pasted image 20211108172417.png]]

Ahora Overhead, se globaliza y  se trata más de trabajo. 

![[Pasted image 20211108172500.png]]

Se puede dar que a un proceso no se le de CPU, especialmente si este tiene prioridad muy baja. 

# Algoritmos de Itineración
![[Pasted image 20211108173142.png]]
Para medir y comparar, utilizaremos los tiempos

## Tiempos más importantes:

- Tiempo de Ejecución. Desde que doy click al acceso directo, hasta que terminó. (**no** es el tiempo de uso de la cpu, ⚠ no confundir!!!!!)
	![[Pasted image 20211108174012.png]]
- Tiempo de Espera, existen hartos lugares desde los que se puede estar esperando
- Tiempo de Respuesta, desde que llega a la ready, hasta que le doy por primera vez la cpu.


![[Pasted image 20211108173320.png]]

> 🌟 ![[Pasted image 20211108174533.png]] 🌟

## Algoritmos

1. [[FCFS]]
2. [[SJF]]
3. [[Round Robin]]
4. **Falta!!!!**

## Colas

1. [[Varios Niveles]]
2. [[MFQ]]

# Multiprocesamiento

![[Pasted image 20211117170710.png]]

![[Pasted image 20211117171341.png]]

![[Pasted image 20211117171429.png]]

![[Pasted image 20211117172403.png]]