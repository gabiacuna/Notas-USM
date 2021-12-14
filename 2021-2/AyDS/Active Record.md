# Active Record

> Actualmente se considera un antipatrón, ya que se sacrifica demasiado.

Es una forma de implementar [[ORM]].

Gestiona la persistencia de datos y los metodos asociados para la utilización y recuperación de los mismos.

## Utilidad

- Representación de modelos y sus datos asociados.
- Rep. de las asociasiones entre modelos.
- Rep. de las jerarquías de herencia entre esos modelos.
- Permite la validación de los modelos antes de que se hagan persistentes en la base de datos.
- Operaciones de bases de datos a travez de métpdps especificos que manipulan objetos.

>  Un objecto que envuelve una fila de una base de datos o vista, encapsula el acceso a la base de datos y agrega lógica de dominio a estos datos.

![[Pasted image 20211214162608.png]]

Un obj se encaga tanto de los datos como de comportamiento. Gran parte de estos datos  son persistentes y deben almacenarse en una BD. 

## Caracteristicas

- Los datos se mapean con BDR, pero nada impide que sean almacenados en otro tipo de BD.
- AR funca bien cuando las operaciones son de tipo CRUD y otras similares.
- Cuando aumenta la complejidad de las operaciónes, AR puede volverse dificil de usar.
- AR se acopla fuertemente al diseño de la BD.