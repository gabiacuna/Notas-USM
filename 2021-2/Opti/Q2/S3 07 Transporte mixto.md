# El problema de trasporte utilizando la menor cantidad de rutas
>![[Pasted image 20210921113609.png]]

## Ejemplo :

![[Pasted image 20210921113619.png]]

Tambien podemos plantearnos utilizar la menor cantidad de rutas.

![[Pasted image 20210921113715.png]]

Ahora se introduce una variable de decicion binaria para ver si se utiliza una ruta o no. Mientras que las de desicion continua nos dice la cantidad de unidades transportadas por la ruta. 

> Si la variable de desicion binaria es 0, la de de decision continua tambien debe serlo. Y si la binaria es 1, la de desicion continua debe der $\geq$ 0.

![[Pasted image 20210921114209.png]]

La var de desicion bin debería ser $Y_{ij}$!!!!!!!

Estas son las restricciones tradicionales del problema de transporte:
![[Pasted image 20210921114304.png]]

Estas son restricciones de activación, que son nuevitas:
![[Pasted image 20210921114406.png]]

Ojito que estan mal las restricciones. los primeros 5 deben ser 5000, los siguientes 5 6000 y los ultimos 5 2500.

# El problema de trasporte considerando costos fijos y rutas variables en las rutas.

> ![[Pasted image 20210921114655.png]]

## Ejemplo :

![[Pasted image 20210921114752.png]]

![[Pasted image 20210921114850.png]]

Lo único que cambia es la FO:
![[Pasted image 20210921114916.png]]

[[Qin2]]