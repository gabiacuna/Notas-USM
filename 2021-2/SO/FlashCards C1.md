#deck1

#SO 
# V/F

## C1 2019-2

El vector de interrupciones determina la causa del evento a través de un registro especial. ::: Falso: determina la causa según la dirección del vector a la cual se transfiere el control.
<!--SR:!2021-11-12,11,230!2021-11-01,7,261-->

La memoria caché constituye la memoria más rápida de un sistema computacional. ::: Falso: La memoria más rápida son los registros. -> Los de la CPU!
<!--SR:!2021-12-04,33,281!2021-10-28,3,261-->

Multiprogramación es lo mismo que multiprocesamiento.::: Falso: Multiprocesamiento requiere la existencia de varios procesadores.
<!--SR:!2021-11-24,23,281!2021-10-28,3,262-->

El cambio de contexto se realiza sin la intervención del SO. ::: Falso: El cambio de contexto se realiza ejecutando código del SO en modo kernel.
<!--SR:!2021-11-14,13,262-->

Hyper-Threading es una característica de procesadores Intel que no quiere apoyo del SO. ::: Falso: Los SO’s deben estar optimizados para poder sacar provecho de esta característica.
<!--SR:!2021-10-26,3,250!2021-11-03,2,242-->

Los sistemas de los 80’s se caracterizaban por ser grandes, complejos y costosos. ::: Falso: Se caracterizaban por ser funcionales, prácticos y simples.
<!--SR:!2021-11-02,1,202-->

Los eventos de interrupción producidos por el timer son un buen ejemplo de traps. ::: Falso: Las traps son producidas por software.
<!--SR:!2021-11-26,25,282-->

En términos generales la implementación de µKernel no tiene ninguna desventaja. ::: Falso: El desempeño es menor debido a los sobre carga de funciones del sistema.
<!--SR:!2021-11-16,15,250!2021-10-28,3,262-->

Enmascarar interrupciones se refiere a bloquear la ejecución del interrupt handler. ::: Falso: Se refiere a deshabilitar interrupciones ante otros eventos.
<!--SR:!2021-10-26,1,210!2021-11-03,2,242-->

Ante una interrupción el SO guarda la información de los registros de apoyo en el stack. ::: Verdadero.
<!--SR:!2021-10-26,3,250!2021-11-25,24,282-->


## C1 2020-1

Las generaciones pasadas de computadores gestionaban la transferencia de bytes (lectura / escritura) mediante la CPU. ¿Esta situación afecta la multiprogramación? Fundamente.
?
Respuesta: Si la CPU se encarga de gestionar la transferencia de bytes significa que estará ocupada realizando operaciones de E/S en un 100%, lo que no permite sacar provecho a través de la multiprogramación.
<!--SR:!2021-11-03,2,238-->
<!--SR:!2021-11-03,2,238-->

<!--SR:!2021-11-03,2,242!2021-10-28,3,262-->

¿Cuál es la diferencia clave entre un trap y una interrupción?
?
Respuesta: Un trap se produce de forma síncrona con la ejecución de un programa. La interrupción ocurre de forma asíncrona y es producida por un evento externo. Un trap es producido por hw y una interrupción por el sw.
<!--SR:!2021-11-10,9,242-->

¿Cuál es el objetivo de una llamada al sistema?
?
Respuesta: Una llamada al sistema permite a los procesos de usuario acceder y ejecutar funciones que son parte del sistema operativo y que se encuentran en el kernel.
<!--SR:!2021-11-08,7,222-->

Para un desarrollador de software una llamada al sistema se ve igual a cualquiera otra llamada a un procedimiento de una librería. ¿Debería el desarrollador saber cuáles son llamadas al sistema? ¿Bajo qué circunstancias?
?
Respuesta: Desde el punto de vista de la programación no debería ser necesario que el desarrollador sepa que llamada a un procedimiento resulte en una llamada al sistema. Podría ser necesario desde el punto de vista del desempeño, dado que le uso de llamadas al sistema produce overhead producto de los cambios de contexto. El uso excesivo aumentará el tiempo necesario para poder ejecutar un programa.
<!--SR:!2021-11-02,1,202-->

¿Por qué una hebra otorgaría de manera voluntaria la CPU al utilizar yield?
?
Respuesta: Las hebras de un proceso son cooperativas. Una hebra puede ejecutar yield por el bien de la ejecución de un proceso.
<!--SR:!2021-11-02,1,202-->

Mencione una ventaja y una desventaja del uso de hebras en espacio de usuario.
?
Respuesta: Una ventaja corresponde a la eficiencia. No se necesitan traps al kernel para cambiar entre hebras. Una desventaja es que si una hebra se bloquea, el proceso completo se bloquea.
<!--SR:!2021-11-02,1,202-->

## C1 2020-2

Las generaciones pasadas de computadores gestionaban la transferencia de bytes (lectura / escritura) mediante la CPU. ¿Esta situación afecta la multiprogramación? Fundamente.
?
Respuesta: Si la CPU se encarga de gestionar la transferencia de bytes significa que estará ocupada realizando operaciones de E/S en un 100%, lo que no permite sacar provecho a través de la multiprogramación.
<!--SR:!2021-11-03,2,238-->
<!--SR:!2021-11-03,2,238-->

<!--SR:!2021-11-03,2,242!2021-10-28,3,262-->

¿Cuáles son las actividades que debe realizar el manejador de llamadas al sistema?
?
Respuesta:
• Localizar argumentos.
• Copiar los argumentos en memorial del kernel.
• Validar los datos para prevenir errores.
• Copiar los resultados en memoria de usuario.
<!--SR:!2021-11-02,1,202-->

¿Una API es lo mismo que llamadas al sistema?
?
Respuesta: No. Las llamadas al sistema son propias de cada sistema operativo. La API es una biblioteca con llamadas estándares que permite a las aplicaciones abstraer de cómo se generan las llamadas al sistema a través de interrupciones.
<!--SR:!2021-11-12,11,242-->

Indique una ventaja y una desventaja de los SO’s estructurados como micro kernel.
?
Respuesta:
• Ventaja: El SO es fácil de extender. Nuevos servicios se agregan en espacio usuario y no es necesario modificar el kernel.
• Desventaja: Posible impacto en el desempeño debido a la sobrecarga de funciones y mensajería entre los servicios.
<!--SR:!2021-11-02,1,202-->

En Unix podemos ejecutar $date en un terminal para obtener la fecha, pero si ejecutamos $exec date desaparece el terminal. ¿Por qué?
?
Respuesta: Al ejecutar $ exec date se reemplazo el proceso terminal por el comando date. Cuando termina, no hay terminal esperando por él.
<!--SR:!2021-11-02,1,202-->

¿Por qué razón memoria compartida es más eficiente que paso de mensajes?
?
Respuesta: El IPC paso de mensajes requiere la intervención del kernel. Usar memoria compartida solo lo requiere durante la creación.
<!--SR:!2021-11-03,2,222-->

# Capitulo 1 -  Introduccion, historia, y Topicos avanzados

## Miden la eficiencia de un sistema

Latencia ::: Cuánto demora una tarea en terminar.
<!--SR:!2021-11-13,12,230!2021-10-28,3,262-->
Throughtput ::: Números de operaciones por unidad de tiempo.
<!--SR:!2021-11-02,1,202-->
Overhead ::: Trabajo extra realizado.
<!--SR:!2021-10-26,1,210!2021-11-03,2,222-->
Justicia ::: Cómo se reparte la eficiencia entre los usuarios.
<!--SR:!2021-11-11,10,230!2021-10-29,4,241-->
Predictibilidad ::: La eficiencia debe mantenerse en el tiempo.
<!--SR:!2021-11-11,10,230!2021-10-28,3,262-->


# Capitulo 2 - Organización y Diseño.
## Cambio de modo

### ¿Cambio de modo de kernel a usuario o usuario a kernel?

Inicio de un nuevo proceso. ::: Kernel -> Usuario.
<!--SR:!2021-11-13,12,230!2021-10-28,3,262-->
Retorno desde un evento de interrupción. ::: Kernel -> Usuario.
<!--SR:!2021-11-15,14,262-->
Cambio de contexto. ::: Kernel -> Usuario.
<!--SR:!2021-11-03,2,222-->
Mensajería asíncrona. ::: Kernel -> Usuario.
<!--SR:!2021-10-28,3,230!2021-11-27,26,282-->

¿Qué es una API?
?
Es una biblioteca con llamadas al sistema estándares que permite a las aplicaciones abstraer la implementación de las llamadas al sistema a través de interrupciones de software y de cómo se transfieren los parámetros y resultados entre el espacio de direcciones de los procesos y el kernel y viceversa.
<!--SR:!2021-11-10,9,221-->


## HAL

¿Qué es HAL?, ¿A qué criterio de diseño/desafío de un SO impacta?
?
Es una interfaz que contiene configuraciones y operaciones específicas de procesadores. Impacta en la portabilidad.
<!--SR:!2021-11-09,8,222-->

## Servicios Estructurados

### Tipo de Kernel

SO’s modernos se dicen híbridos. ¿Qué significa? Mencione 2 ejemplos.
?
Se refiere a la forma en cómo se estructura el SO en términos de sus servicios utilizando lo mejor de las técnicas de kernel monolítico, micro kernel, capas y módulos.
• Linux y Solaris usan monolítico junto a carga dinámica de módulos.
• Mac OS híbrido, por capas. Aqua UI junta al ambiente de desarrollo Cocoa.
<!--SR:!2021-11-02,1,202-->