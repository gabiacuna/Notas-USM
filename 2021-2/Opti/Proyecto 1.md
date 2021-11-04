# Inventario (Multiples periodos)

**Fechas:**  

-   Entrega de video de 7 minutos: domingo 10 de Octubre
-   Entrevista grupal sobre el proyecto: semana del lunes 11 de Octubre

  
**Descripción:**  

1.  Desarrollar un programa computacional que genere instancias aleatorias o con algún patrón determinado del problema bajo estudio. Considerar diversos tamaños del problema (pequeños: del orden de las decenas, medianos: del orden de los cientos y grandes: del orden de los miles).
    

        Considere variando número de instancias y variables.

2.  Resuelva las instancias generadas usando algún solver de programación lineal. Puede usar alguno visto en clases o algún otro. Justifique su decisión.
    
3.  Compare resultados considerando la calidad de la solución y el tiempo utilizado para obtenerla.
    
4.  Estudie casos factibles(existe solución factible) e infactibles (no existe solución factible). Identifique la razón de la infactibilidad.
    

  

**NOTA:** Analice los resultados pensando en responder preguntas como:

1.  ¿Cuáles son los parámetros más importantes del modelo y cómo afectan en la resolución del problema?
    
2.  ¿Cómo crece el costo computacional (en tiempo y/o memoria) al momento de ir aumentando el tamaño del modelo?
    
3.  ¿Bajo qué circunstancias el modelo no encuentra solución? ¿Qué factores son los más importantes para que exista solución?

![[Pasted image 20211007175012.png]]

# Dialogo video
-   Se desarrolla un código para generar instancias factibles e infactibles.
    
-   Se generan diferentes arreglos para almacenar, la función objetivo, las restricciones y las restricciones de positividad.

En cuanto al código creado para generar las instancias del problema, decidimos crear dos. Uno genera instancias con soluciones factibles y otro que genera soluciones infactibles. Ambos son iguales en estructura, pero varía la forma en la que se generan los parámetros aleatorios. Estos inician importando la librería renadom para generar las instancias aleatorias y definiendo la variable n como la cantidad de períodos.  Luego se definen los arreglos donde se almacenarán la función objetivo y las restricciones.  Para generar la cantidad de variables en relación al tamaño de la instancia, se realiza un ciclo for, que itera desde 1 hasta n, por lo que en ese mismo ciclo se realiza la función objetivo y todas las restricciones. cabe notar que todas las variables se multiplican por un coeficiente igual a 1, ya que es un requerimiento del formato de lpsolver.

Procedimiento de generación de instancias. 

Procedimiento de generación de aleatoriedad de los parámetros de cada instancia
