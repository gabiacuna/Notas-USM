# Evasión

Ahora no atacamos las propiedades, sino que revisamos dinamicamente las asignaciones de los recursos.

Podemos construir un proceso examinador de las cargas de recursos.

El sistema debe manejar información a priori:
- Cada tarea declara el máximo número de recursos que necesita.
- Dinámicamente se examina el estado de asignaciones.
- El estado de asignación queda definido por los recursos disponibles, asignados y demandados.
- El análisis se realiza cuando una tarea solicita un recurso disponible.
- Si su asignación deja el sistema en estado seguro, se realiza.
- Sistema en estado seguro no tiene deadlock.
- Sistema en estado inseguro podrı́a tener deadlock.

> ## Estado Seguro
> Debe existir al menos una secuencia de asignación de recursos para todas las tareas del sistema tal que para cada una de ellas se puedan asignar los recursos que aún necesitan.

La idea es _evitar entrar en un estado inseguro_.
- Cantidad de instancias por tipo de procesos:
	- **Una** → Grafo de asignación de recursos.
	- **Múltiples** → Algoritmo del banquero.

## Grafo

Ahora agregamos un **arco de demanda** Que indica que T en algun momento va a demandar el recurso de tipo R. (Ti - - -> Ri)

- Indica que la tarea podrı́a requerir un recurso.
- Se convierte en requerimiento cuando se requiere un recurso.
- Se convierte en asignación cuando el recurso es asignado.
- Cuando se libera el recurso, se convierte en demanda.
- Los recursos deben ser demandados a priori.

Aplica solo para una instancia de recursos
![[Pasted image 20211207105036.png]]

Podemos asignar R2 a T2 primero, y genera un estado inseguro, ya que estamos a punto de generar un ciclo.

Cuando una tarea hace una petición de un recurso, Puede ser resuelta solo si al convertir un arco de requerimiento en un arco de asignación **no se genera un ciclo en el grafo**.

## [[Banquero - Evadir]]