# Kahoot

1. No es parte de las componentes de una hebra
	1.  CPU, es del sistema
	2.  Si tiene, Contadores, id, registros y stack. 
2. Las hebras de un mismo proceso tienen id's distintos. Dos hebras comparten el proceso cuando ambas son creadas en el mismo proceso, ej multiplicacion de matrices. Si comparten los datos, el codigo y recursos asignados. 
3. Un proceso con múltiples hebras tiene más de un posible orden de ejecución. Ya que depende de como el itinerador manda los procesos. La ejecución de las hebras no es determinista.
4. Se necesita más de un procesador para tener paralelismo.
5. El kernel es el encargado de almacenar los estados internos de una hebra.
6. Los estados de una hebra son:
	1. Finished
	2. Running
	3. Ready
	4. No Walking!!!! 
7. Las hebras pueden crearse tanto por el kernel  como por el usurio.
8. El modelo de hebras una a una es costosa, ya que se deben crear el doble de hebras.
9. Paralelismo y concrrencia no es lo mismo. Paralelismo es la ejecucion de mas de una tarea al mismo tiempo, y concurrencia es ir turnando la ejecucion de dos o mas procesos o hebras.

# Ejemplo 1

![[Pasted image 20211104224336.png]]

Programa base: 
![[Pasted image 20211104224359.png]]
S guardará el valor de la sumatoria.

Viendo el problema, plantemos que existiran 5 threads, donde cada una calculará el producto entre los diferentes elementos. La gracia de hacer esto, es que cada profducto se realiza de manera separada, y eventualmente se podrían realizar de manera paralela.

![[Pasted image 20211104224708.png]]

Exit que guarda el valor de el resultado. 

ahora le asignamos la func multi a cada thread

![[Pasted image 20211104224901.png]]

![[Pasted image 20211104225256.png]]