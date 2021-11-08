# Inicio del sistema e Interrupciones

## Inicio del sistema

Los dos grandes objetivos de la BIOS son, _validar el hardware_ ( que todos el hardware de la arquitectura donde esta montada este funcionando de forma correcta) y _cargar el bootloader_.

![[Pasted image 20210922193008.png]]

> El **kernel** (núcleo) es el set de servicios que son parte del SO y se deben ejecutar con un privilegio de tipo SO.
> p 1254 del libro:
> ![[Pasted image 20210922194122.png]]

Luego del bootloader, lo se carga el login y las cosas que generan una interfaz, para luego seguir cargando los procesos necesarios. (por un tema de sensacion del usuario, para que este no tenga que esperar tanto a que el sistema parta). Tambien en caso de que el usuariuo no sea validado, hay servicios que es mejor cargarlos una vez que ya esta validado el user.

![[Pasted image 20210922195324.png]]

## Interrupciones

![[Pasted image 20210922195910.png]]
-> toda la forma de trabajar de los SO's modernos es a travez de la gestión de las interrupciones. 



- Estos eventos cambian el flujo normal de la ejecucion de una función.
- Si hay un set de interrupciones desplegadas, debe haber un forma de visualizarlas con un ID y codigo para arreglarlas. Ademas se continua la ejecución. Por lo que el SO debe ser capaz de detener una ejecucion, sacarla de la CPU, arreglarla, volver a cargarla y que parta desde el punto en el que fue detenida. 
- En la misma ejecucion de una instruccion se produce el evento de inerrupción.

> El proceso es una instancia del programa en ejecucion que tiene mas cosas ademas de las instrucciones.

![[Pasted image 20210922200416.png]]
- Organizacion de las interrupciones :
![[Pasted image 20210922201255.png]]
El sistema se construlle pensando en que se conocen todas las interrupciones posibles del sistema.

- Las interrupciones no son siempre por problemas (las llamadas al sistema son interrupciones).

> Las interrupciones son eventos que debe resolver el SO

![[Pasted image 20210920182523.png]]

![[Pasted image 20210920182932.png]]

![[Pasted image 20210920183829.png]]

La CPU ejecuta instrucciones y lo que se ve son los hilos del sistema por detras.

Para construir al gestoniador de eventos de interrupcion existen dos formas que veremos mas adelante. 

![[Pasted image 20211006175915.png]]

Cada evento interruptor tiene una rutina que maneja ese proceso

> ! Gestionar a travez de interrupciones


### Vector de interrupciones
 
Lo podemos ver como una tabla que tiene 1 id para cada interrupcion y un par para cada id que es un salto a una direccion de memoria, donde esta almacenada la rutina que resuelve el evento de interrupción. Como:
La tabla (el vector) esta en la parte baja de la RAM, que esta asignada a so.
![[Pasted image 20211006180553.png]]

ejemplo:
Vector de interrupciones para el intel pentium:
![[Pasted image 20211006181609.png]]

Si solo se tiene un procesador, se espera a que se termine de ejecutar una interrupción para revisar las siguientes. Por lo tanto si empiezan a llegar más interrupciones estas se enmascaran y encolan (fondo de la tabla).
\- Si se pueden manejar hartas interrupciones a la vez si se cuenta con multiples nucleos/procesadores.

En vez de la tabla, aveces se utiliza el Coprocessor() , o Cause Registers, sin importar la causa, siempre se salta a la misma dir de memoria, y en esa region hay una gran rutina que resibe como input el id, y ahí resuelve.

![[Pasted image 20211006184605.png]]

Cuando el sistema es interrumpido, se debe 'sacar una foto' del momento en el que se interrumpe, para no reiniciar el proceso cada vez que este se interrumpe.

Dependiendo de la arquitectura del hardware existen diferentes procesos que dan apoyo a los registros. Para guardar los datos se define un stack, que el so almacena los datos para **todos** los procesos.

![[Pasted image 20211008010630.png]]

El stack guarda informacion de lo que va ocurriendo en el mismo, este es del SO y guarda info de gestión de los procesos.

![[Pasted image 20211008011556.png]]
![[Pasted image 20211008012037.png]]