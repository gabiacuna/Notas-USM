# Kahoot Ayu Mie

1. El sistema operativo se encarga de establecer la comunicación ==entre el software y el hardware de un sistema.== -> tambien gestiona la memoria del sistema, asignar CPU a los procesos y decidir quien usa la CPU y quien no, cuanta con algoritmos de decicion, entre otras cosas. 

2. Conservar bateria es uno de los objeticos fundamentales del SO en dispositicos moviles.

3. Rol de arbitro del SO : 
    * Asignar equitativamente los recursos entre los distintos programas
    * Ahislar a los usuarios y los programas entre si
    * Es como un juez que asigna de manera justa los recursos del computador a una carga de procesos

4. Rol de ilusionista del SO :
    * Un programa siente que todos ls recursos del compu son para el.
    * Un programa siente que los recursos del computador son infinitos.

5. EL criterio de portabilidad, es que un SO funcione independientemente del hardware en el que esta instalado.

6. Seguridad -> el SO cuenta con multiples seciones para que algunos usuarios de un sistema compartido no tengan acceso a los archivos de los otros usuarios.

7. Confiabilidad -> El SO hace lo que tiene que hacer

8. Troughtput, es la cantidad de operaciones por unidad de tiempo.

9. Latencia, es lo que demora cada tarea en completarse.

10. En el sistema Batch las aplicaciones se ejecutan una a la vez.

11. En la decada de los 60 aparece el concepto de multiprogramacion.

12. Multiprogramacion : 
    * Ejecutan múltiples tareas tratando de dejar la CPU lo menos ociosa posible.
    * Disminuir el tiempo de ejecucion de un conjunto de tareas.
    * Aumenta el uso de la CPU
    * **No** se ejecutan dos procesos en la misma unidad de tiempo, pero tenemos la ilusion de que se esta ejecutando mas de una cosa a la vez ([[paralelismo]]).

# Ejercicios

## Ejercicio 1 Jue

> Agregar la foto unu

-> entrada y salida se refiere a entrada y salida de datos de un programa. (este es tiempo en el que no se está usando la CPU, por eso se marca en el gráfico)

El eje x son ciclos de reloj (una unidad de tiempo)

\* Tomaremos P0-P3 de arriba a abajo y se encuentran en la cola en ese orden.

Debemos definir una cola de procesos.

Inicio de la cola de procesos:
 
$$ Q_0 = P_0P_1P_2 $$

> cada vez que un proceso esta utilizando la CPU debo preguntarme, ¿Que estan haciendo los otros procesos? La respuesta es, el ultimo proceso no tachado.
> Si el ultimo no tachado es E/S, se agrega a la ejecución. Si es uso de CPU, se agrega a la cola.

Cola total del ejercicio:

$$ Q_0 = P_0P_1P_2 + P_1P_0P_2 $$

Esto considera que cada proceso tiene su propio hardware de entrada y salida. 


[[SO]]