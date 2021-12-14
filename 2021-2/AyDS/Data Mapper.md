# Data Mapper

## Contexto 

- Los obj y BDR tienen diferentes mecanismos para _estructurar los datos_
- Colecciones y herencia, no son directamente moldeables en las BDR
- Cuando se construye un sistema con mucha lógica de negocio, es valioso mantener estas reglas ordenadas para organizar mejor los datos y el comportamiento que conlevan.
- Si un componenete ORM basa su deseño en objetos en memoria que se relacionan demasiado con la estructura de la BD, los cambios en uno tienden a complicarse en el otro.

## Contexto - Propuesta

- Propone la utilización de una capa de sw intermedia que separa los objetos en memoria de la BD.
- Su responsabilidad es **transferir los datos entre las dos capas y aislarlas**.
- Con data mapper los objs,
	- No necesitan saber que hay una BD presente.
	- No necesitan manejar consultas a la BD
	- No neceistan conocimiento del esquema de la BD

> ## Definición
> Una capa de mapeadores que mueve datos entre objetos y una fuente de datos mientras los mantiene independientes unos de otros y del mapeador

![[Pasted image 20211214164736.png]]
Fuente: https://www.martinfowler.com/eaaCatalog/dataMapper.htm


## Fundamentos

- La fx principal de un DM es la **separación entre el dominio y el origen de datos**.
- Existen muchas formas de construir las capas que realizan el mapping.
- Cuando se quiere actualizar datos, el mapper extrae los datos desde un objeto y los almacena en una fuente de datos.
- Los mappers necesitan una variedad de estrategias para manejar las clases que se convierten en múltiples campos, ...
- Las estrategias varian de acuerdo al conocimiento que se tenga del origen de datos.

## Uso

- Un sist puede tener uno o más DM implementados
- En un sistema grande tiene sentido dividir los metodos en una agrupación de multiples mappers.
- La pp oportunidad para utilizar el patrón DM es cuando se quiere que el esquema de la BD y clases/objs evolucionen de forma independiente.
- Facilitar el diseño de un sistema que debe imp estrictas reglas de negocio.
- Minimizar el impacto de la BD en los objetos (y vicecersa).

### De acuerdo al tipo de sistema

- Si esta en desarrollo y su proposito pp es hacer CRUD, lo mejor es usar [[Active Record]]
- Para satisfacer estrictas reglas y procedimientos de una empresa, DM podría ser una mejor opción.

### De acuerdo al ecosistema tecnológico

- Si se esta construyendo un sitema  en un dominio nuevo, [[Active Record]] es lo recomendable.
- Si se requiere integrar una aplicación en una organización madura y con sist ya establecidos -> DM





