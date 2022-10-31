o denominación, es una necesidad en cualquier sistema computacional (no solo dist)

Queremos que el sistema de Nameing sea *escalable*, *eficiente* y *tolerante a fallas*.

## Tipos de nombres

- Direcciones
- Identificadores
- Nombre amigable para humanos

## Que es un nombre?

> Cadena de bits o caracteres que se utiliza para referirse a una entidad (Meta: Compartir **recursos** y **comunicación**).

Para operar sobre una [[Entidad]] es necesario acceder a ella a travez de una punto de acceso. El nombre de un punto de acceso se denomina **dirección**.

Los nombres pueden ser independientes de la ubicacion, cambiar su direccion, otros pueden contener info sobre la ub. de la entidad.
![[Pasted image 20221019204357.png]]

### Dirección

Un nombre que se refiere a un punto de acceso en un sistema de comunicación.

### Identificadores

- Único y para identificar a **una** sola entidad.
- Un identificador siempre se refiere a la misma entidad (nunca se reutiliza).

La ambiguedad puede ser util, ya que nos puede servir para referirnos a un conjunto de entidades. 
![[Pasted image 20221019204744.png]]

Esto se lo podems dar a un balanceador de carga.

### Nombre amigable para humanos

Generalmente representado como una cadena de caracteres, ej: direccion de un archivo, `gabi/home/desktop/tokens.txt`; google.com...

## Sistemas de nombres

> Mantiene un enlace de nombre a la dirección.

Vinculacion : asociasion entre un nombre y un objeto.

\* La tabla centralizada con (nombre, dirección), no funcionará para sistemas distribuidos.

### Que debe contener un sistema de nombres:

- Def de un conjunto de nombres permitidos
- def de un conjunto de entidades a nombrar
- def la asociación entre nombres y entidades
- def como se localizan las entidades en un SD.
- oculta al usuario los detalles de cómo y dónde se localiza una entidad en la red.
### Dominios de nombres compuestos

Son doms de nombres utilizados para acceder a un recurso desde una URL.
![[Pasted image 20221019205433.png]]

