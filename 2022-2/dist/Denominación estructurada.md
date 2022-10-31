# Espacios de Nombres

Los nombres se organizan en un espacio de nombres, que requieren una definicion sintáctica.

Los espacios de nombres para nombres estructurados se pueden representar como un grafo dirigido etiquetado.
![[Pasted image 20221020125324.png]]
- Nodos hoja: Rep una entidad nombrada. *Puede almacenar estado*.
- Nodo de directorio: almacena una tabla con bordes salientes (id de nodo, etiqueta de borde) y tiene un identificador asociado.
**Path name**: secuencia de etiquetas correspondientes a los bordes del camino.
# Resolución de Nombres

> Proceso de buscar un nombre.

ej: path: `lab1/lab2/lab3`, lab1 se busca en la raiz del nodo, l2 se busca en el nodo con l1 y asi sucesivamente.
![[Pasted image 20221020125556.png]]
-> Se ve que home se busca en n0, steen en n1 y keys en n4.

**Enlace simbolico**, representa una entidad por un nodo hoja, almacenando un camino absoluto.

## Resolucion de nombres en múltiples espacios de nombres

Ej NFS (network file system) que es independiente del SO.
![[Pasted image 20221020125924.png]]
Se tienen espacios de nombres extranjeros (como los esp. de nombres de servidor 1 y servdor 2). Punto de montaje, que es el nodo que almacena al identificador del nodo en el cliente, y el nodo de directorio en el esp. de nombres extranjeros. 
![[Pasted image 20221020125838.png]]

![[Pasted image 20221020130142.png]]

## Resolución iterativa de nombres

Puede ser util si la probabilidad de primer o segundo intento es alta, x ex cuando se tienen pocas maquinas.
Donde el cliente (que va a buscar un dominio), le pregunta a cada servidor si conoce el domino, conectando los procesos.
![[Pasted image 20221020130332.png]]

## Otra resolución de nombres - No recursivo

Controlado por el servidor, donde el serv conecta a sus pares si no puede resolver el nombre por si mismo

Este sobrecarga la red

## Otra resolución de nombres - Recursivo

Controlado por el servidor, si no puede resolver el nombre contacta al servidor superior, responsable de un prefijo grande del espacio de nombres.

Siempre tiene un mejor resultado en promedio que el no recursivo.

-> Si el recurso no cambia mucho, el **caché** es muy útil!!.

## Comparación de costos de comunicación Iterativo vs Recursivo

![[Pasted image 20221020130836.png]]

En el caso recursivo gastamos en tiempo de espera, mientras que en el iterativo gastamos en sobrecargar la red. La resolucion recursiva suele ser más barata con respecto a la comunicación.

# Denominación basada en atributos

Aveces los clientes no saben el nombre de una entidad en particular que buscan, pero tienen info que la describe.
- Se supone que una entidad tiene una colección de atributos

## Sistemas de nombres basados en atributos

*tb conocido como servicios de directorio*.

El diseño de atributos tiene que hacerse manualmente en la mayoría de los casos.

Ej, recursos descritos como un triplete (sujeto, predicado, objeto)
![[Pasted image 20221020131436.png]]
![[Pasted image 20221020131425.png]]

Estos sistemas requieres una busqueda exaustiva a traves de todos los descriptores. Ahora el problema esta en **encontrar el recurso**.

Se pueden aplicar varias técnicas para evitar una busqueda exaustiva, como indexación. Comunmente se combinan nombres estructuradoos con nombres basados en atributos.

### Caso de estudio LDAP (Lightweight Directory Access Protocol)

Se tiene una base de info del directorio DIB, con todas las entradas del directorio. A cada atributo le decimos, nombre distinguido relativo (RDN). La lista de RDN en secuencia conduce a una jerarquía de la coleccion de entradas de directorio -> Arbol de info del dir (DIT).
![[Pasted image 20221020202930.png]]
![[Pasted image 20221020202936.png]]

