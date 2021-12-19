# Page Controller

## Consideraciones

- [[Mvc]] usualmente se enfoca en la sep. entre modelo y vista, no pescando tanto al controlador.
- Si la sep entre controlador y vista no es critica, se omite
- En agunas app la vista y el controlador estan separados ya que la vista es para el cliente y el controlador desde el servidor.

## Contexto

- Como estructurar el  controlador para apps web medianamente complejas, permitiendo la flxibilidad y reutilización mientras evitan la duplicación de codigo?

## Def

> Un objeto que maneja una solicitud para una página específica o una acción en un sitio web

## Diagrama

![[Pasted image 20211215112511.png]]
[Fuente](https://martinfowler.com/eaaCatalog/pageController.html)

## Observaciones

controlador recibe una solicitud de la página, extrae cualquier dato relevante, invoca cualquier actualización al modelo y reenvía la solicitud a la vista.
-	La vista depende del modelo para recuperar datos
-	Se crea un controlador para cada pag de la app web

## Beneficios

- **Simplicidad**, los cont solo tienen que trarar con un alcance limitado y pueden ser simples
- **Desempeño**, No existen cuellos de botella al usar dist controladores ya que desminuyen los recursos compartidos.
- **Reutilización**