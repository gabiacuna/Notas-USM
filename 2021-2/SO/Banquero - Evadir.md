# Banquero

- Utilizado para múltiples instancias de tipos de recursos.
- Cada tarea debe demandar a priori el máximo uso de recursos.
- Una tarea puede tener que esperar.
- _Cuando obtiene todos sus recursos los utiliza y los libera._

El problema es que ya no se pueda avanzar.

### Algoritmo del Banquero

⭐ Al correr el algo se logra determinar si el sistema esta en un estado seguro!

Sean n = número de tareas y m = número de tipos de recursos.

- **Disponible**:
	- Vector de largo m.
	- Si Disponible [j] = k, hay k instancias disponibles de Rj .
- **Max**:
	- Matriz n × m.
	- Si Max [i, j] = k, la tarea Ti puede requerir a lo más k instancias del recurso tipo Rj .
- **Asignado**:
	- Matriz n × m.
	- Si Asignado [i, j] = k, Ti tiene asignado k instancias de Rj .
- **Necesita**:
	- Matriz n × m.
	- Si Necesita [i, j] = k, la tarea Ti puede necesitar k instancias adicionales del recurso tipo Rj .
	- Necesita [i, j] = Max [i, j] - Asignado [i, j].

1. Defina los vectores Trabajo y Fin de largo m y n respectivamente:
Trabajo = Disponible
Fin[i] = false, for i = 0, 1, ..., n − 1
2. Busque un i tal qué:
Fin[i] = false
Necesitai ≤ Trabajo.
Si no existe, saltar al paso 4.
Si existe, pasamos al paso 3.
3. Ejecute:
Trabajo = Trabajo + Asignado[i]
Fin[i] = true
Volver al paso 2.
4. Si Fin[i] = true para todos los i, el sistema está seguro.

En caso que se requiera realizar una nueva solicitud debemos:
1. Definir el vector Solicitud i para la tarea que está solicitando.
Si Solicitudi [j] = k, la tarea Ti quiere k instancias de Rj .
2. Si Solicitudi ≤ Necesitai avanza. Caso contrario, error.
3. Si Solicitudi ≤ Disponiblei avanza. Caso contrario, espera.
4. Ejecute:
Disponible = Disponible - Solicitudi
Asignadoi = Asignadoi + Solicitudi
Necesitai = Necesitai - Solicitudi
5. Volvemos a correr el banquero.
Si es seguro, se realiza la asignación.
Caso contrario, se debe esperar y restaurar el estado anterior.

