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