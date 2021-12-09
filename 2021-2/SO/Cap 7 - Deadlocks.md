# Deadlocks
 > Es un ciclo de espera entre un conjunto de tareas que se estan ejecutando.

Donde las tareas esperan algo que no puede ocurrir. Y esa accion no ocurre por que el proceso esta esperando otra cosa. Esto es como un trencito de espera donde las tareas se quedan atrapadas.

> Se entra en un **deadlock** cuando el ciclo se cierra. (Tarea A depende de que termine la tarea B y la tarea B depende de que termine la A).


- Cada tarea espera que otra realice alguna acción.
- Dicha acción no puede ocurrir. 
- Es un desafío para el desarrollo de aplicaciones multi hebras.

### Ejemplo
![[Pasted image 20211201114102.png]]

---

- Deadlock e [[Inanición]] se relacionan con la vida de un proceso o hebra. 

> En la [[inanición]] se queda detenido por un tiempo indefinido. Pero pueden avanzar, sabemos que si aplicamos envejecimiento si puede avanzar en algun momento.

- Deadlock es [[inanición]], pero tiene una condición más fuerte. Cuando se entra a un deadlock, **no** se puede continuar. 
- El problema es que ambos no ocurren siempre. 
- Herramientas de testing no descubren directamente esto. 
- Será necesario un esfuerzo adicional en el desarrollo. 

El deadlock se puede producir por las entradas y salidas, pese a que una solucion este bien programada en cuanto a variables de sincronización.

### Condiciones generales

- [ ] Un sistema con un número finito de recursos. _Siempree_
- [ ] Los recursos se distribuyen entre distintas tareas en competición.
- [ ] Distintos tipos y cada uno puede tener distintas instancias.
- [ ] Ciclos de CPU, archivos, E/S, memoria (de dispositivos de almacenamiento), etc. ->  hablaremos de recursos.
- [ ] Si una tarea solicita un recurso, la asignación de cualquier instancia de éste satisface la solicitud realizada.
- [ ] Un recurso no puede ser utilizado si no ha sido asignado.
- [ ] Se pueden solicitar tantos como se necesiten.
- [ ] El total de solicitados no puede exceder al total disponible.

La utilización de los recursos sigue la secuencia:
- **Solicitud**: La tarea espera mientras la solicitud sea respondida.
- **Uso**: Se utiliza el recurso.
- **Liberación**: Se libera el recurso.

\* Solicitud y Liberación requieren uso de llamadas al sistema.

### Condiciones para el Deadlock

1. **Exclusión Mutua**: Una tarea utilizando un recurso a la vez.
2. **Espera y Retención**: Tarea en espera retiene el recurso.
3. **No se puede quitar**: Recursos no pueden ser quitados.
4. **Espera circular**: Existe un conjunto de tareas que esperan, y cada tarea espera por un recurso que tiene otra tarea.

> Las 4 condiciones deben ocurrir de forma **simultanes**.

Un proceso solo no puede generar un deadlock!.

### [[Grafo de asignación]]

## ¿Que Hacemos?
1. Asegurarnos que el sistema **nunca** entrará en deadlock.
	- [[Prevencion para deadlocks]]
	- [[Evasión para deadlocks]]
2. Permitir que el sistema entre al deadlock y recuperar el sistema.
	- [[Algoritmo de detección]]
	- [[Mecanismo de recuperación]]
3. Ignorar el problema y lo vemos como que no hubiese ningun problema.


