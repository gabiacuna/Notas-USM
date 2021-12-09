# Algoritmo de detección

Vamos a tener las variantes del grafo y del algoritmo del banquero para determinar si hay un deadlock o no.

- Si tenemos una instancia por tipo de recurso, utilizaremos el grafo _wait-for_.
- Los nodos son tareas
- Ti → Tj . Si Ti espera por Tj .
- Se invoca periodicamente en busca de un  ciclo. Si hay ciclo, hay deadlock.
- Suele ser bastante costoso, por que sin importar si es el grafo o el banquero modificado, se debe buscar constantemente y tenemos que definir una tasa de ejecución y un tasa de recuperación.

![[Pasted image 20211208102414.png]]

Sacamos los recursos y dejamos las tareas. en el grafo de la derecha hay deadlock. _Todas las tareas que forman parte del ciclo estan en deadlock_. En este caso, las tareas T1 -> T2 -> T3 -> T4 forman deadlock, al igual que las tareas T1 -> T2 -> T4. La única tarea que no esta en deadlock es T5.

## [[Banquero - Evadir]] modificado.
Ahora utilizaremos un algoritmo del [[Banquero - Evadir]] modificado.

- **Asignado**:
	- Matriz n × m.
	- Define número de tipos de recursos asignados.
- **Disponible**:
	- Vector de largo m. Indica las instancias disponibles.
- **Solicitud**:
	- Matriz n × m.
	- Indica las siguientes solicitudes de las tareas.

Ya no tenemos la matriz de los maximos, ya que no es necesaria.

1. Defina los vectores Trabajo y Fin de largo m y n respectivamente:
Trabajo = Disponible
For i = 1, 2, ..., n. If $Asignado_i \neq 0$ then Fin[i] = false
Caso contrario Fin[i] = true
2. Busque un i tal qué:
Fin[i] = false
Solicitudi ≤ Trabajo.
Si no existe, saltar al paso 4.
3. Ejecute:
Trabajo = Trabajo + Asignadoi
Fin[i] = true
Vuelva paso 2.
4. Si Fin[i] == false para algún valor de i, el sistema está en deadlock.
If Fin[i] = false, entonces Ti está en deadlock.
Requiere realizar operaciones con un orden de O(m × n2 )

> ejemplo en tablet unuuuuuu

## Sobre el uso de la detección

- Cuándo y qué tan seguido utilizamos los algoritmos?
	- Qué tan seguido puede ocurrir un deadlock?
	- Cuántos procesos hay que restaurar?
- Si se invoca de forma arbitraria:
	- Podrı́a encontar una situación con muchos ciclos.
	- No podrı́amos determinar quién causo el deadlock.

Mientras más grande es el problema, más dificil es recuperarlo.