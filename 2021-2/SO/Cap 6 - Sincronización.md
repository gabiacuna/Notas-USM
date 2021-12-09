# Acceso Sincronizado a Objetos Compartidos

1. Conceptos Básicos
2. Problema : demsiado Ron
3. Herramientas

## Conceptos Básicos

Consideramos un proceso con 2 hebras, si tienen variables compartidas a las que ambas le modifican sus valores, tenemos problemassss.

> La itineración de hebras es no determinista

---
### Ejemplo
Consideramos otro proceso con 2 hebras.
![[Pasted image 20211129150840.png]]Para saber los posibles valores para x, necesitamos descomponer el código, donde la idea es analizar las operaciones atómicas que lo componen. 
Tenemos los posibles escenarios:
![[Pasted image 20211129150954.png]]

---

> ### Problema
> Acceso concurrente a objetos compartidos.
> - Comportamiento del programa es indefinido, por lo que el resultado puede variar en cada ejecución. Tenemos una **incoherencia de datos**.

### [[Condición de Carrera]]


- **Seccion Crítica** : Código donde se accede al objeto compartido
- Toda sol a un problema de este tipo debe cumplir con 3 cosas:
	1. **Exclusión mutua**: Solo 1 entra a la sección crítica. _Propiedad de seguridad_
	2. **Progreso** : Las solicitudes de acceso deben avanzar.  _Propiedad de vivacidad_
	3. **Espera acotada**: Si se solicicta entrar, la espera es acotada. _Propiedad de vivacidad_

- Construir la solución es pega del programador
	- Puede llevar a errores y otros problemas
- SO's modernos entregan las herramientas para sincronizar. **No** resuelven el problema ellos.



## Problema: [[Demasiado Ron]]

## Herramientas

- [[Objetos Compartidos]]
- Variables
	- [[Locks]].
	- [[Variables de Condición]].
	- [[Semáforos]].
- [[Liveness]]