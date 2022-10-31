## Greedy
Representación:
	Asignación factible de entidades a habitaciones, en el formato:
	```c++
	vector<vector<int>> solution; // room, associated entity
	```
Función miope: Asignar la siguiente entidad a la primera entidad posible a la primera habitación disponible que cumpla con las restricciones duras y minimice la fo.
Punto de partida: entidad con eid 0.
Función de evaluación: FO.

## HCMM

![[Pasted image 20221029170543.png]]

```cpp
sc = initial_instance;
local = false;
while (local){
	sn = best neighbour;
	if f(sn) > f(sc){
		sc = sn;
	} else {
		local = true;
	}
}
```

```cpp
instance best_neighbour (instance inst){
	
}
```