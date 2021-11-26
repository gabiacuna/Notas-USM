# Método Stepping-Stone

> Analiza el efecto en los costos al transportar una unidad por cada ruta no utilizada en la solución inicial.

1. Paso 1: Por cada celda desocupada, identificar un ciclo en el tableau de transporte
2. Paso 2: Calcular el cambio unitario $e_{ij}$ para cada celda desocupada.
	1. Enumerar las celdas del ciclo partiendo por la celda desocupada en sentido contrario a las manecillas del reloj.
	2. Calcular eij sumando los valores de las celdas impares y restando las pares.
3. Paso 3:
	1. Si el problema es de minimización y todos los eij son no-negativos, entonces la solución es óptima.
	2. Si existen valores negativos de eij, identificar la mejor celda (la más negativa)
4. Paso 4:
	1. A la celda seleccionada anteriormente asignarle todo lo posible. Esto corresponde al mínimo entre las celdas pares.
	2. Restar lo asignado a cada celda par y sumar el valor a cada celda impar.