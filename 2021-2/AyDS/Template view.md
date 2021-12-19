# Template view

## Definición

> Renderiza información dentro de un HTML mediante marcadores insertos en una página HTML.

## Diagrama

![[Pasted image 20211215155207.png]]
[Fuente](https://www.martinfowler.com/eaaCatalog/templateView.html)

## Descripción General

- Incorporar datos dentro del codigo HTML, a travez de marcadores en la pagina. Como fragmentos de PHP/ASP/JSP

## Implementación

- Se puede implementar de muchas formas. Por ej usando etiquetas similares a las `<>`.
- Muchos lenguajes proveen un set de etiquetas predefinidas, pero actualmente es posible encontrar lenguajes que permiten al usuario personalizar dichas etiquetas según sus necesidades.
- `<? ?>`,`< % %>`, etc

## Cuando usar TV?

- Separar la lógica del dominio de la lógica de presentación
- reutilizar estructura común en visras, con datos desplegados dinamicamente y caria de acuerdo a lo que pide el user.
- tiene ventaja para los diseñadores gráficos, ya que permite crear interfaces sin preocuparse de los datos.

## Ventajas

- **Independencia**, Separa datos de estructuras de codigo para implementar interfaces gráficas.

## Desventajas

- **Dependencias**, si una logica es implementada incorrectamente nada funciona.