# Patrones Estructurales Objeto-Relacionales

---

# Foregin Key Mapping

## Problema
- En un sistema, muchos obj se relacionan entre sí.
- Para almacenar estos objetos en la base de datos es vital conservar las **referencias**.
- Haiendo las cosas mas complicadas, un objeto puede almacenar una colección de objetos que se referencian entre sí.

## Definición

> Mapea una asociación entre objetos a una referencia de clave foránea entre tablas

## Diagrama
![[Pasted image 20211214180410.png]]
Fuente: https://www.martinfowler.com/eaaCatalog/foreignKeyMapping.html

# Association Table Mapping

## Problema

- Las BDR no permiten tener más de un valor para un objeto.
- Se pueden mapear asociasiones de objetos 1:M con FKM

## Definición

> Mapea una asociación entre objetos como una tabla con claves foráneas a las tablas que están involucradas en la asociación

## Diagrama

![[Pasted image 20211214181454.png]]

# Single Table Inheritance

## Problema

- Las BDR no tienen soporte de herencia.
- Se debe evitar expresar herencia con muchas tablas, ya que la acer multiples JOIN se verá afectado el rendimiento del sistema.

## Definición

> Representa una jerarquía de herencia de clases como una única tabla que posee columnas para todos los atributos de las múltiples clases involucradas.

## Diagrama

![[Pasted image 20211214181936.png]]

# Class Table Inheritance

## Problema

- BDR no tienen soporte para herencia.
- Se tienen que mapear los objetos para vincular cualquier eemento a la estructura de herencia.

## Definición

> Representa una jerarquia de herencia de clases con una tabla para cada clase

[Ejemplo!!!!!](https://www.sourcecodeexamples.net/2018/05/class-table-inheritance-pattern.html)
