# Prioridades

> Cada tarea tiene un número entero como prioridad, y se le asigna la cpu a la tarea con la prioridad más alta. [[SJF]] es un caso especial de prioridades.

Puede ser,
- **Cooperativo** : Se espera a que termine una tarea aun que llege otra con mayor prioridad.
- **Apropiativo** : Si llega un tarea mientras se ejecuta una con menor prioridad, esta se interrumpe para empezar a ejecutar la tarea nueva. La antigua vielve a la cola ready.

Tambíen sufre de [[Inanición]], y se soluciona con la  _tecnica de envejecimiento_. 
> ### Técnica de envejecimiento
> A medida que pasa el tiempo, se aumenta la prioridad.

## Ejemplo - Todos los procesos llegan al mismo tiempo.

![[Pasted image 20211128171206.png]]

## Ejemplo - Procesos con misma prioridad utilizan RR con q = 2.

![[Pasted image 20211128171316.png]]