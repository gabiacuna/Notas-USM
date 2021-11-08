# Operaciones
![[Pasted image 20211012003949.png]]

Para poder crear procesos utilizamos llamadas a sistema, que dependen de como las implementa cada so. 

![[Pasted image 20211012004045.png]]

Se tiene una jerarquia de procesos:
![[Pasted image 20211012004301.png]]

## Aristas de relaciones entre padre e hijo:
![[Pasted image 20211012004344.png]]

![[Pasted image 20211013171642.png]]
El kernel mencionado hace referencia a 2 ideas:
1. Memoria baja de la ram donde esta el SO ![[Pasted image 20211013171755.png]]
2. ????

![[Pasted image 20211013171901.png]]

## Llamadas al sistema en Unix
![[Pasted image 20211013171926.png]]
[[wait]] se usa para procesos que estan en una jerarquia.

![[Pasted image 20211013172109.png]]
En unix los padres tienen que esperar a sus hijos.

### [[Fork]]
![[Pasted image 20211013172122.png]]

Esto es lo que hace  la shell:
![[Pasted image 20211013172132.png]]

#### Ejemplo
![[Pasted image 20211013172327.png]]
pid es un nombre de variable, esta es de tipo entero

El proceso hijo no sabe cual es su Id, pero para obtenerlo `getpid()`.

![[Pasted image 20211013173224.png]]

![[Pasted image 20211013173236.png]]

Crear el nuevo espacio depende de la gestion de la memoria principal (GMP).

El itinerador esta al tanto ya que esta al tanto de la cola ready, y el proceso nuevo, si no hay un error, queda ahí.

![[Pasted image 20211013173413.png]]

Si meto un nuevo programa, este parte desde el inicio y el espacio se ajusta segun las necesidades.

## Cración / Ejemplos

![[Pasted image 20211013173708.png]]
![[Pasted image 20211013173727.png]]
wait null hace que espere a los hijos 
**ej 2 tareita**
![[Pasted image 20211013180331.png]]
## Otras operaciones
![[Pasted image 20211013180741.png]]
![[Pasted image 20211013180751.png]]
