# Método de distribución modificada (MODI)


1. Paso 1: Definir variables ui para cada fila i y vj para cada columna j 
2. Paso 2: Para cada celda ocupada establecer ui + vj = cij 
3. Paso 3: Fijando alguna ui ó vj calcular todas las variables ui y vj
4. Paso 4: Para cada celda desocupada calcular eij = cij − ui − vj
5. Paso 5: Si el problema es de minimización y
	1. los eij son no-negativos, entonces la solución es óptima
	2. existen valores negativos de eij, identificar la más negativa
6. Paso 6: A la celda seleccionada anteriormente
	1. Asignarle todo lo posible (mínimo entre las celdas pares)
	2. Restar lo asignado a cada celda par
	3. Sumar lo asignado a cada celda impar