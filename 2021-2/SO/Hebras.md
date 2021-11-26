# Def
> Nos permiten separar un proceso en dos o más tareas que pueden ejecutarse de manera concurrente ( o paralela si se cuenta con el hw correspondiente). Eso permite que el tiempo dee cómputo sel proceso disminuya, y se aprovechen de mejor manera los recursos que nos brinda nuestra máquina. Además, permite que algunos procesos se puedan escalar de manera eficiente.

Todas las aplicaciones modernas se estan construyendo al uso de las hebras.

> Tienen el objetivo de separar las tareas internas que tiene un proceso al momento de ejecutarse. 

A diferencia del fork, las hebras son parte del mismo proceso. Si se crean hebras en P0, estas siguen formando parte de P0.

![[Pasted image 20211027180011.png]]

El uso de  hebras, mejoran el desempeño y se pueden obtener calculos más rápidos. Especialmente si se tienen procesadores con hyperthreading.

![[Pasted image 20211103121231.png]]

No hay un nivel más bajo que una hebra. 

![[Pasted image 20211103121347.png]]

A la izquierda esta un proceso simple con una Hebra principal.
-> Cada hebra tiene sus propios [[registros]], [[stack]] y [[PC]]

# Beneficios
![[Pasted image 20211103121623.png]]

No requiere el uso de [[IPC]] -> Todas las hebras forman parte de un mismo proceso, por lo que _comparten una region de datos_.

Es más simple la implementación de hebras que de forks. 

Los cambios de contextos entre hebras, son menos costosos que los cambios de contexto entre procesos. 

Escalabilidad y potenciamiento de una arquitectura actual, con procesadores de multiples nucleos. 

# [[Concurrencia]] con Hebras

![[Pasted image 20211103122344.png]]

Para todos los programas con hebras debemos ser ordenados y utilizar herramientas de sicronizacion cuando se utilizen variables compartidas.

![[Pasted image 20211103122521.png]]

Con esto se ilustra el comportamiento del programa y uso de las hebras.

-> Para implementarlas utilizaremos una [[API simple para Hebras]]

# Estados

![[Pasted image 20211103224120.png]]

Representado con las llamdas al sistema de simple threads. 

1. Creadas
2. Ready, itinerador asigna
3. Running 
4. Si le aplican un yield -> Ready
4. Si le aplican un join -> Waiting -> Ready
5. Finished

Todo esto va dentro del running del diagrama para procesos.

![[Pasted image 20211103224329.png]]

