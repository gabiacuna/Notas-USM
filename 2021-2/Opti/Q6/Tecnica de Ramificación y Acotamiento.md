# Branch & Bound
- Variables enteras

Metodo para resolver problemas de PE

* Resolver relajaciones contiunas del problema entero para acotar la función objetivo. (bound) Para ver que tanto nos conviene seguir o si paramos de explorar.
* Crear ramas agregando restricciones que eliminen los valores no-enteros.

## Ejemplo

![[Pasted image 20211101165741.png]]

Sin la condición de valores enteros (versión relajada), se puede llegar facilmente a la solución, y sería x* = (8.5 , 4.5) z* = 156.5.

> Si el problema ver relajado, no tiene solución, tampoco lo tiene su ver og.

A lo mas la FO va a ser 156.6 en el problema og.

![[Pasted image 20211101170240.png]]

Ahora ramificamos, para esto, se ahisla el punto v3, y se generan 2 ramas, una para x1 <= 8 y otra para x1 >= 9.

![[Pasted image 20211101170405.png]]

Los simplificamos de nuevo, y resolvemos. 

Se puede notar que en la segunda rama, luego de acotar la var x1, se obtien un vector entero.

![[Pasted image 20211101170528.png]]

Ya que P2 es una sol entera, es la primera sol candidata para resolver el problema, y no es necesario que sigamos analizando ese lado. 

Ahora pasamos a ramificar para x2.

![[Pasted image 20211101170721.png]]

![[Pasted image 20211101170733.png]]

Nuevamente tuvimos suerte ya que para p3 tenemos una sol entera. asi que para p4 seguimos ramificando (por x1 ya que nos da un valor no entero). 

* Notar que 144>141 asi que ahora la mejor solución enera es la de p3.

Para seguir ramificando, ahora eliminamos entre 7 y 8 para x1.

![[Pasted image 20211101170946.png]]

![[Pasted image 20211101171018.png]]

Puedo seguir ramificando por p5, para x2. Ahora x2, le eliminamos entre 5 y 6. Ahora queda fijo que x2 = 5.

![[Pasted image 20211101171133.png]]

Ahora ambas llegan a una sol entera asi k terminamos ❤.

![[Pasted image 20211101171248.png]]

Entonces la sol del problema es: x = (6, 6), z = 150.

## Conclusión

- Selección del problema a ramificar afecta eficiencia del algoritmo
- Selección de la variable de ramificación afecta eficiencia del algoritmo
- Fenómeno de variable de ramificación recurrente

- Profundidad máxima del árbol de enumeración puede ser estimada en basa a cantidad de variables y valor máximo que puede tomar cada variable