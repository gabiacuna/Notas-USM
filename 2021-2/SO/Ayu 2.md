# kahoot
1. El inicio de un sistema comienza con la BIOS.
2. Los objetivos de la BIOS son
	1. Cargar el boot loader
	2. Validar que el hardware no tenga problemas
3. Cuando se inicia el sistema, el bootloader busca el kernel del so y lo carga en la memoria.
> El **kernel** es el nucleo del so y se encarga de que exista una comunicacion segura entre el hardware y software.
4. La ocurrencia de un evento se indica a travez de una interrupción.
> **Interrupciones**, son eventos que cortan el flujo normal de instrucciones de cualquier programa. Las interrupciones se ejecutan al toque, no se dejan esperando.
5. Las interrupciones no se producen solo por software.
> Las interrupciones por sw son las traps, y por hardware se les llaman interrupciones.
6. Son ejemplos de traps:
	1. División por cero.
	2. Referencia a memoria invalida.
> Timer, actualiza la zona horaria del sistema. Es una pieza de hardware.
7. La ejecucion de una interrupcion deshabilita las demás interrupciones.
	-> Las interrupciones se ejecutan de inicio a fin sin interrupciones.
8. El vector de interrupciones es una estructura que almacena punteros a distintos interrupts handlers.
9. Cuando el bit esta en 0 estamos en modo kernel por lo que se tiene privilegio del hw. (para 1 se esta en modo usuario).
10. Producen un cambio de modo usuario a kernel:
	1. llamada a sistema.
	2. interrupcioes producidas por el timer.
	3. el comportamiento no esperado de un proceso.
	\- El retorno de un evento de interrupcion realiza un cambio de kernel a usuario.
	
# Ayu 2 - Miercoles

# Llamadas al sistema

Nos permiten acceder a servicios especificos del so. Accedemos a ellas a travez de una API, teniendo cada una su propia IP. El so mantiene las llamadas al sistema mediante una tabla indexada por id.
Ejemplos de llamadas a sistema:
*	mkdir
*	fopen
*	fwrite
*	fork

# Secuencia de una llamada a sistema

Desde que se invoca hasta que se retorna.

![[Pasted image 20211010193614.png]]

# Servicios estructurados

Las llamadas al sistema se pueden catalogar en base al soporte que prestan los distintos servicios del so.
![[Pasted image 20211010193750.png]]
Contabilidad son los servicios que nos dicen el rendimiento de la cpu (lo que se muestra en el task manager).

Los so modernos necesiran una una manera de estructurar los servicios. Dos de ellas son:
1. Kernel Monolitico : Estructurar los servicios de forma que solo el kernel los gestiona.
2. Micro Kernel : intenta alivianarle la pega al kernel y tirar todos los servicios posibles al modo usuario.

## Ventajas y desventajas
|| Kernel Monolítico | Micro Kernel |
|---| --- | --- |
|**Ventajas**| Mayor rendimiento para gestionar servicios, debido a que nos se pasa todo el rato entre kernel y usuario. | Se minimiza la probabilidad de que falle el kernel. Tmb es más facil de extender. |
|**Desventajas**| Si se produce un error en modo kernel es necesario reiniciar el sistema| Se produce overhead producto de la cte comunicación entre modo kernel y modo usuario. |

## Sistemas hibridos

Hoy los so utilizan lo mejor de ambos mundos.

ej:
![[Pasted image 20211010195410.png]]

# Ayu 2 - Jueves
1. El vector de interrupciones determina la causa del evento segun la direccion del vector a la que se redirige. (Esta en el ram del kernel)
2. El coprocesador 0 es un conjunto de funciones, por lo que lo determna a travez de un conjunto de parametros, llamado cause. (estan en la ram del usuario)
3. En una llamada al sistema, hay formas de pasos de parametros:
	1. Registros de apoyo en la cpu (4 registros en los que se guarda info)
	2. Se cargan en el stack y el so las extrae
	3. Se pasa la dirección de memoria.
4. El inicio de un nuevo proceso provoca un cambio de modo, el kernel tiene control total sobre el hw, por lo que cuando inicia un proceso, este necesita que se le asigne espacio y para hacer esto se hace el cambio a modo kernel.
5. Es un servicio de contabilidad del so:
	1. Cuanta memoria utiliza un proceso
	2. El porcentaje de uso de la CPU
	3. La cantidad de memoria disponible en el disco duro.
6. La bios esta en la placa madre. Primero revisa todo el hw y despues carga el bootloader.
7. Las llamadas al sistema se usan para acceder a los servicios del so.
8. El cambio de contexto de raliza con la intervencion del so.
9. HAL (_hw abstraction layer_) impacta en la portabilidad. Es una api que abstrae el hw, ahora son fx y me desentiendo de interactuar directamente con el hw.
10. El Hal necesita drivers para comunicarse con hw nuevo. Los drivers le dicen como usar el hw nuevo. Para asegurar la portabilidad de kernel monolitico es necesario el HAL y los drivers.
11. Cuando se virtualiza un so guest si puede hacer llamadas al sistema. Para hacerlo, se comunica con el host que le da permisos para hacerlas (le traspasa la comunicación al kernel).
12. Sobre la virtualización:
	1. Beneficios:
		- Ahorro de recursos
		- Portabilidad
		- Multiples SO corriendo en el mismo HW
	2. Desventajas:
		- Disminución de rendimiento del HW

