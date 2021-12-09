# Recuperación

> Dos opciones:
> - Finalizar tareas.
> - Quitar recursos.

- Finalización:
	- Terminar todos los procesos en deadlock.
	- Terminar un proceso por vez hasta eliminar el ciclo.
- ¿En qué orden deberı́amos elegir?
	- Prioridad y/o tipo de tarea.
	- Uso de CPU utilizado y/o restante.
	- Uso de recursos.

Todas estas deciciones le pegan al diseño del so

## Quitar recursos
- Seleccione una vı́tctima.
- Quitar los recursos y restaurarlo.
- Volver a un estado seguro.
- Reiniciar procesos. 
- Puede ocurrir [[inanición]]. -> si seleccionamos siempre la misma victima.
- Guardar el número de restauraciones como id. -> para evitar la [[inanición]]