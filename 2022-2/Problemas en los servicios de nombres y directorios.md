## Fraccionamiento

Ningun servidor de nombres puede tener todos los nombres y atributos de toda la red (menos en internet).

> Datos del servidor de nombres son particionados segun el dominio.
-> Para equiparar tareas.

## Replicación

Un dominio suele tener más de un servidor de nombres. Estos mejoran la disponibilidad y rendimiento, pero aumenta la complejidad.

## Almacenamiento en caché

Los servidores pueden almacenar en caché las resoluciones de nombres realizadas en otros servidores.
-> evita contactar repetidamente al mismo serv de nomb. para buscar nombres idénticos.

El sw de busqueda de clientes tb puede almacenar un caché los resultados de las solicitudes anteriores.

Esto puede llevar a problemas si una direccion se actualiza entes de que el caché elimine el registro.