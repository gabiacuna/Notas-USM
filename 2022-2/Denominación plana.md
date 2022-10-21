Es la forma más simple de un [[Sistemas de nombres]].

# Flat naming

## Soluciones simples para redes de área local.

### [[Broadcasting]]
- Multicast: localizar entidades en redes punto a punto (a un grupo en especifico).
> Ventajas: simplicidad, sin mantenimiento.
> Desventaja: escalabilidad (ineficiente cuando el sistema crece), ancho de banda desperdiciado, interrupciones de hosts no involucrados.
### Punteros de reenvío
Cuando una entidad se mueve de A a B, deja una referencia en A a su nueva ubicacion en B.

! Para encontrar es necesario recorrer toda la ruta.

> Ventajas: simplicidad, migración transparente para el cliente.
> Desventaja: Una cadena puede volverse larga -> ubicación costosa. Mantenimiento de localizaciones indeterminadas, vulnerabilidad a enlaces rotos.

## Enfoques basados en el hogar

- Ubicación de inicio: realiza un seguimiento de la ubicacion actual de la entidad.
- ej: IP Movil
- Agente local: la comunicacion se dirige inicialmente a este agente.
- care-of-address: direccion temporal en otra red. El agente local realiza un seguimiento de esta informacion.
> Ventaja: Mecanismo oculto para aplicaciones (transparencia).
> Desventajas: la ubicacion del agente local puede estar lejos de la entidad.

![[Pasted image 20221019223725.png]]

## Tablas hash distribuidas (DHT)

- Cuerda: espacio identificador de m bits (128, 160 bits).
- Identificador elegido aleatoriamente para nodos y claves para entidades.
- Se asigna una clave a un nodo.
![[Pasted image 20221019223956.png]]

> Ventajas: Busqueda escalable. [[Churn]] no afecta a toda la red.
> Incovenientes: Complejidad en el mantenimiento.

## Enfoques jerárquicos

- La red se divide en dominios y se puede subdividir en subdominios.
- Dominio unico de nivel superior.
- Cada dominio D tiene un nodo de directorio que realiza un seguimiento de las entidades en ese dominio.
- Una entidad puede tener varias direcciones (replicación)
![[Pasted image 20221019224604.png]]
![[Pasted image 20221019224626.png]]
![[Pasted image 20221019224637.png]]