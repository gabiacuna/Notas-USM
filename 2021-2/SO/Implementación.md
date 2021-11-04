![[Pasted image 20211103222950.png]]

Meter hebras en la implementación no es tan simple, se debe reaplicar todo lo que habiamos definido para procesos.

Para las hebras aparece la [[TCB]].

## 2 Tipos de Hebras

![[Pasted image 20211103172232.png]]
Igual se requiere de ayuda del so para crear las hebras, y se realizan a travez de llamadas al sistema

![[Pasted image 20211103172242.png]]

Nos referimos a los diferentes procesos del so. Construidas a nivel de rutina.

![[Pasted image 20211103172515.png]]

> Para que exista una real concurrencia, es necesario que el SO tambien tenga una implementación de estas. Si el so no ganariamos nada, no se tendría ni concurrencia ni paralelismo. 

# Modelos
![[Pasted image 20211103172529.png]]
## Muchos a Una

![[Pasted image 20211103172550.png]]

Solo tenemos un gestionador de eventos, si le llegan muchas solicitides, las resolverá de forma secuencial. Y si se tiene una arqui con multimples procesadores, no se estarán aprovechando.

Una version de solaris utiliza esto. Pero es muy especifico, pero actualmente las arquitecturas tienen más de un procesador.

La cantidad óptima de hebras para so, depende de la arquitectura en la que me vaya a instalar. No hay una regla.

Si se bloquea la hebra tipo kernel, sono el proceso.

## Muchos a Muchos

![[Pasted image 20211103173107.png]]

No es muy utilizado[[Implementación]]

## Una a Una ⭐

![[Pasted image 20211103173331.png]]

Si una hebra se bloquea, las otras pueden continuar, en una arquitectura multicore. pto 4 es el único problema de esto. En arquitecturas antiguas esto era un impedimento importante.

A todas las hebras que el usuario cree, el so crea una tipo kernel.


---

# Ejemplos

Tomando el modelo con el que implementemos el SO.

Incorporar hebras, impacta en todo nivel del diseño. Todas las defs debemos hacerlas a nivel de hebras.

![[Pasted image 20211103173758.png]]

![[Pasted image 20211103173812.png]]

![[Pasted image 20211103174842.png]]

Ahora no hablamos solo de procesos, si no que tambien de hebras.

![[Pasted image 20211103174908.png]]

⚠ Intentar hacer!

![[Pasted image 20211103222805.png]]