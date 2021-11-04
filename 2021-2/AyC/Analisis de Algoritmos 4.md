Medimos el costo contra la cantidad de elementos contra los que se compara.
![[Pasted image 20210920122431.png]]
El costo de busqueda del 18, son 4 comparaciones. (contra 33, 11, 20 y 18). Si el 18 no esta en el arbol, cuesta 3 comparaciones insertarlo, ya que se compara con 33, 11 y 20; cuando se llega a una hoja, se inserta.
-> el costo de busqueda es el costo de insercion + 1, *si el elemento no se ha movido*. Este no sería el caso de un AVL.
> Por eso, este es el caso para un ABB sin borrado, solo busqueda e inserciones.

El costo promedio de busqueda exitosa es :
![[Pasted image 20210920122741.png]]
Con $I_n$ la suma de caminos internos. 
> profundidad es la distancia desde la raiz, y el costo de busqueda exitoso es esta profundidad + 1.
Para el costo promedio de la busqueda infructuosa es :
![[Pasted image 20210920122947.png]]
Lo que es la profundidad del nodo externo correspondiente. (son n+1 nodos externos)

*Recordar la propiedad:*
$$E_n = I_n + 2n$$

# Análisis Amortizado
Llega a salvarnos cuando el analisis de caso promedio es tan pesimista que no es realista. Este es para ver el panorama despues de realizar cierta cantidad de operaciones.
Asumimos  una EDD con n operaciones. El costo amortizado es el tiempo promedio por operacion, luesgo de ejecutarlas a todas. Si hay una operacion constosam, se promedia con el resto, por lo que no tiene un gran impacto. 

## Ejemplo traslado en bicicleta.
Suponer que debemos trasladarnos todos los días al lugar de estudio:
![[Pasted image 20210920125614.png]]
Que nos conviene? el transporte publico o la bici?

Si son pocos día, convendrá el transporte publico, pero si amortizamos la bicicleta, aumentando la cantidad de días que se utilizan (pago 100 el primer día, pero luego paso d dias pagando 0, versus 1 todos los dias con el transporte publico).

Para n días, Costo TP : n dolares
Para la bici : ![[Pasted image 20210920130253.png]]

## Implementacón de Colas usando Pilas.

![[Pasted image 20210920130546.png]]
Se utilizan 2 pilas, $S_1$ y $S_2$.
* Q.ENQUEUE(x): Se implementa haciendo $S_1$.push(x).
* Q.DEQUEUE(): Si $S_2$ está vacı́a, primero se traspasan todos los elementos de
$S_1$ a $S_2$ (uno por uno, usando $S_2$ .PUSH($S_1$ .TOP()) y $S_1$ .POP()). Luego, se hace 
$S_2$.POP().

Pese a que algunos dqueue serán caros, pero si utiliza la edd por harto tiempo, el tiempo promedio de la operacion será constante. El proceso es eficiente, no en cada operación.

Un buen costo amortizado no nos garantiza nada en el paso a paso, pero si al largo plazo. 

## Incrementar un contador binario

Pensando en un contador A que es un arreglo de bits, este empieza en 0. Inicialmente estará así:
![[Pasted image 20210920132046.png]]
Solo se puede incrementar, no se puede ni restar ni resetear. Solo sumar 1.
El algo para sumar 1 es :
![[Pasted image 20210920132129.png]]
Cuando encuentra el primer 0 se detiene, y cambia el elemento actual por un 1 ( si no se ha acabado el arreglo). Y a medida que recorre cambia los 1 por 0. Así va escribiendo los numeros en binario OoO.
[[AyC]]