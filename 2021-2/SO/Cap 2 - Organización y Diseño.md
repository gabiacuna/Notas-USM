# Capítulo 2 ~  Organizacion y Diseño

[ppt](https://aula.usm.cl/mod/resource/view.php?id=2488221)

Podemos tener diferentes escenarios, y hay diferentes servicios que debemos incorporar e incluso priorizar, por ej, si hay 10 servicios y solo puedo incorporar 3, como los elijo?
Como ordeno un SO enforcado en sus servicios.

Contenidos del cap:
1. Inicio del Sistema e Interrupciones  
2. Modo Dual de Ejecución  
3. Llamadas al Sistema  
4. Servicios Estructurados  
5. Virtualización

---
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

# Modo dual de Ejecución
![[Pasted image 20211008012105.png]]
 Modo kernel es el modo de sistema operativo, y requiere soporte de hardware, que se llama bit de modo.
 La mayoría de los programas tienen permisos tipo usuario, pero llamadas a sistema requieren modo so.
 
 ![[Pasted image 20211008012234.png]]

Cuando se corre una instruccion, se revisa si se tienen los permisos correspondientes, y si los tiene, se ejecuta.

usuario -> kernel
![[Pasted image 20211008012257.png]]

Cuando se producen estis eventos, se entrega el control de la cpu al so. 
![[Pasted image 20211008013257.png]]
![[Pasted image 20211008013304.png]]


![[Pasted image 20211006122057.png]]

![[Pasted image 20211006122110.png]]

![[Pasted image 20211006122125.png]]

Se implementa en hardware, es un bit, 0 para kernel, 1 para tipo usuario. Este bit se valida para cada ejecución de instrucciones.

El cambio de modo de usuario a kernel es el mas comun, y ocurre cuando se realizan las interrupciones.

![[Pasted image 20211006122340.png]]

Esta figura puede servir para las interrupciuones sincronas.

![[Pasted image 20211006122416.png]]

![[Pasted image 20211006122514.png]]
![[Pasted image 20211006122532.png]]

Upcall : Es una forma del sistema de informar siertos eventos

# Llamadas al sistema

Para acceder a los servicios del so, lo realizamos a travez de una API

API -> capa de asbstraccion entre los servicios del so y los distintos programas en diferentes lenguajes.



![[Pasted image 20211006123659.png]]

Ejemplo de una llamada al sistema.

![[Pasted image 20211006123739.png]]

\- SYSCALL es lo que realiza realmente la llamada al sistema.

![[Pasted image 20211006124124.png]]

![[Pasted image 20211006124143.png]]

(2) hardware trap -> interrupción
Entre los  pasos 3 y 4 es la llamada al sistetema

![[Pasted image 20211006124417.png]]

La mas utilizada es el registro, para la dirección.

![[Pasted image 20211006124428.png]]

![[Pasted image 20211006124440.png]]

La comunicacion es para ir paralelizando y coordinar los procesos.

# Servicios Estructurados

![[Pasted image 20211006125031.png]]

![[Pasted image 20211006125106.png]]

\- Contabilidad aquellas llamadas que permiten obtener info del estado actual del sistema, por ejemplo el task manager

![[Pasted image 20211006125258.png]]

![[Pasted image 20211006125308.png]]

- La mirada de capas : 0 hardware, 8 usuario. Los servicios en las capas superiores utilizan los de las capas inferiores.
## Kernel Monolitico
![[Pasted image 20211006125317.png]]
Dice en parte ya que actualmente los SO toman lo mejor de dos mundos, y son hibridos.

![[Pasted image 20211006125453.png]]

El so debería funcionar soble cualquier hardware, y de esto se encarga el HAL.
El HAL es mucho codigo y se encarga de ver toda la arquitectura del compu.

![[Pasted image 20211006125502.png]]
Esta es una mirada de capas o niveles c:

> ![[Pasted image 20211006130045.png]]
> Más que en procesadores, es en la arquitectura completa del compu.

![[Pasted image 20211006130120.png]]

Los drivers son para E/S.
La cantidad de drivers afecta en el tamaño del SO, la carga dinamica es la posibilidad de ir a buscarlos a internet, descargarlos e instalarlos.

Un HAL malo, podría funcionar solo para una arquitectura.

![[Pasted image 20211006130636.png]]

La comunicacione entre distintas partes del servicio suelen ser complejar, por lo que son más propensas a errores. Si el kernel falla, el So falla.

## Micro Kernel

![[Pasted image 20211006153051.png]]

Intenta mover todos los grupos de servicios al modo usuario, para que no sea necesario ejecuratlos con privilegio de kernel.

No se dejan con privilegios para ser ejecutados.

![[Pasted image 20211006153101.png]]

Grupos de servicios más criticos se dejan en el kernel, y el resto que no necesitan del SO para ser ejecutados, se dejan fuera, con permisos de usuario

![[Pasted image 20211006153113.png]]

Los mecanismosde mensajeria se implementan a travez de llamadas al sistema, por lo que añadir un mecanismo de comuinicacion extra va a generar mas eventos de interrupcion solo para comunicar entre dois servicios.

## Sistemas Híbridos

![[Pasted image 20211006154006.png]]

ejemplos:
![[Pasted image 20211006174424.png]]
![[Pasted image 20211006174436.png]]

---
![[Pasted image 20211006174338.png]]

Las politicas pueden cambiar con el tiempo, pero los mecanismos no!, estos definen la naturaleza de un so.

# Virtualización
![[Pasted image 20211008150153.png]]

Se puede levantar otro SO dento de un So, al que llamamos host. De forma  concurrente o paralela, dependiendo de la arquitectura.
![[Pasted image 20211008150505.png]]
Que es lo que tiene que hacer una gestionadora de maquinas virtuales(VMM) para lograr lo que queremos? -> lograr el efecto de que un so est instalado dentro de un compu real.

En teoria se pueden tener más de una maquina en paralelo, se tienen distinros kernel, en el mismo hardware, por lo que la gestioonadora se lleva la mayor carga.

## Tipos de implementación de VMM
![[Pasted image 20211008165917.png]]
Tipo 0 es standard, es casi una implementacion al nivel del compu. ya no se ocupa mucho.


![[Pasted image 20211008170218.png]]

Tiene que simular todo lo visto previamente en el capitulo (casi todo esta relacionado con las interrupciones). Estos So no se relacionan directamente con el hw, pero **no lo saben**. El unico que se comunica directamente con el hw es el so host.

Funca como un mapeador para los eventos y gestion de interrupciones.

La respuesta de la VMM depende de como el host gestiona los recursos y de como el guest cree que los esta gestionando.

![[Pasted image 20211008170226.png]]

El so esta utilizando el disco del compu. Pero es un disco virtual. (manejado por la VMM).
El inicio es darle play. 

![[Pasted image 20211008170831.png]]

La cpu esta ejecutando las instrucciones del so visita.

> Ambos modos se ejecutan en modo unsuario del host, aun que en si mismos el kernel piensa que es kernel.

![[Pasted image 20211008171859.png]]

la vmm se transforma en la herramienta gestora de interrupciones para el so guest. (como su vector de interrupciones). Si se requiere ejecutar una instruccion de tipo SO, puede ser que sea necesario cambiar de modo en el host.

![[Pasted image 20211008172301.png]]

* Trap son las interrupciones generadas por el so. 
* La VMM responde como si fuera el hw para el so guest.

![[Pasted image 20211008173527.png]]

-> La proteccion es un minimo!!!!!
[[cap2]]

[[cap2]]
#SO  