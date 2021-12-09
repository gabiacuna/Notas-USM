# Grafo de asignación
Podemos definir el deadlock mediante un grafo.
- Modela la asignación de recursos del sistema.
- Está formado por un conjunto de vértices (V) y arcos (E).
- V está particionado en dos conjuntos:
	- T = {T1 , T2 , ..., Tn }. Tareas del sistema.
	- R = {R1 , R2 , ..., Rn }. Recursos del sistema.
- Arco de Solicitud: Ti → Rj .
- Arco Asignación: Rj → Ti .

![[Pasted image 20211206180533.png]]

En este caso no hay deadlock, ya que cuando T3 usa R3, lo libera y lo usa T2, libera R1, R2 y R3, por lo que ahi T1 puede usar R1 y se ejecuta.

> - Si un grafo no tiene ciclos, no hay deadlock. (ciclos cerrados por el orden de las flechas)
> - Si un grafo tiene ciclos:
> 	- Si hay una instancia por tipo de recurso, existe deadlock.
> 	- Si hay varias instancias, existe la posibilidad de deadlock.

![[Pasted image 20211206181117.png]]

El ciclo se forma por que T3 solicito el recurso R2

![[Pasted image 20211206181541.png]]

