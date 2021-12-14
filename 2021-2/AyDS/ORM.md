# Object-relational Mapping
## ORM

## Motivación

- La mayoría de las apps de sw empresariales quieren consultar BD de datos para realizar CRUD
- Techs y sistemas de gestion de bd pueden cambiar con el tiempo.

## Propuesta

- Usar patrones orientados a la **persistencia de datos**.
- Facilitar la gestión de datos a travez de su manipulación mediante objs y métodos de las apps de sw.

## Definición

- Técnica usada para interpretar datos desde un SBDR a objetos de una app.
- Se llama orm al componente de sw que usa esta tecnica.
- Se puede consultar una BD _sin la necesidad de escribir las consultas de forma directa_

---

## Modelo

![[Pasted image 20211214161345.png]]
fuente : https://guides.codepath.com/android/activeandroid-guide

## Características

- Conjunto de funcionalidades que traducen los requerimientos a consultas de base de datos.
- Vincula los atributos de los objetos con las entradas de una BDR.
- Se debe considerar el diseño tabular de las BDR, mientras que los objetos tienden a tener estructuras jerarquicas, por lo que para aplicar ORM se deben considerar las transformaciones necesarias para la representación de los datos.

### Ventajas

- Facilidad de uso
- Abstracción de la BD usada.
- Facilita mantenimiento del código.
- Proporcionan mecanismos de seguridad para prevenir accesos malintencionados a las BDs

### Desventajas

- Impacto en el rendimiento, al trabajar con grandes volumenes de datos.
- Requiere aprender a escribir operaciones usando algún componente de ORM.

