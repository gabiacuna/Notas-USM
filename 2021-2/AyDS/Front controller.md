# Front controller


## Contexto

- Estructurar un controlador para aplicaciones web complejas, donde se pueda tener reutilización y flexibilidad mientras se evita la duplicación de código?

## Definición

> Un controlador que maneja todas las solicitudes de un sitio web

## Diagrama
![[Pasted image 20211215130126.png]]

[Fuente](https://martinfowler.com/eaaCatalog/frontController.html)

## Observaciones

- FC junta todas las peticiones en un solo objeto
- Usualmente delega peticiones a [[Page Controller]] de cada página.

## Beneficios

- **Simplificación**, simplifica el desarrollo cuando la lógica de las peticiones es complicada.
- **Eficiencia**, centralización minimiza la duplicidad de codigo.
- **Opotimización**.