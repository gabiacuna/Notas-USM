# Prevención

Ya que el deadlock pasa si se cumplen las 4 condiciones al mismo tiempo, con que se rompa una, se acaba el deadlock.

Ahora queremos limitar las 4 condiciones. Algunas de las acciones a realizar:

1. Exclusión mutua **no** requerida para recursos compartidos.
2. Obligar que las tareas **no** estén reteniendo para solicitar recursos.
3. Si una tarea está reteniendo y solicita un recurso que no se puede asignar inmediatamente, **se libera el recurso retenido**.
4. Imponer un orden en la solicitud de recursos por parte de las tareas.
