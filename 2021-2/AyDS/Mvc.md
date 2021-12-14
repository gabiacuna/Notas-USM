# MVC

Si utilizamos una misma clase para gestionar datos y elementos de interfaz de usuario, se genera confusión y dificultades. -> en código y organización.

Para soluciónar, separamos las partes constituyentes de este tipo de apliaciones en 3 elementos

> Modelo, Vista, Controlador.

Es un **patrón de arquitectura**.

![[Pasted image 20211214154232.png]]

## Modelo

- Metodos para hacer CRUD a una fuente de datos
- Gestionar la lógica del dominio de la app web.
- En una página puede existir más de un modelo.

## Vista

- Intefaz gráfica de usuario de la app web
- Utiliza los datos proporcionados por el modelo para representarlos en la iu.
- para web de implementa con HTML y CSS

## Controlador	

- Define el comportamiento de una aplicación web. 
- Procesa peticiones HTTP.
- Es intermediario entre vista y modelo, recupera datos desde el modelo y los entrega a la vista.
- Puede usar e invocar metodos de multiples modelos.
- Puede utilizar multiples vistas para responder una petición

## Evolución

- Moti : Separar responsabilidades.
	- Si no se separan, cuando crezca una app, los cambios serán más complejos.
- Fue propuesto og en el contexto de las apps de escritorio.

---

## Variantes

### HMVC

Donde una vista es utilizada en diferentes partes o de forma repetida.

- Hirearchical MVC
![[Pasted image 20211214155246.png]]

### MVP

- Controlador -> presentador.
	- Encargado de la comunicación
- No tiene logica de negocio, solo invoca las func requeridas del modelo
- Model View Presenter

![[Pasted image 20211214155614.png]]

### MVVM

- Controlador -> Viewmodel
	- La logica de la vista se mueve al viewmodel (simplifica la vista)
	- Una view se relaciona con un viewmodel
- Model View View Model

![[Pasted image 20211214155947.png]]

---

## Comentarios Finales

- Cada componente de MVC puede ser apoyado con otros patrones.
- No especifica como implementar dicha separación.
- Favorece la mantenibilidad de código y delegar responsabilidades en el desarrollo.
- Evita introducir defectos en el sw por la poca legibilidad de un código que consolida todos los aspectos del sitio en una misma clase. 