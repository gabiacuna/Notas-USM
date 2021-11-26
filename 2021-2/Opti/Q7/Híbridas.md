# Técnicas Híbridas

Integración de enumeración y verificar la consistencia local.

Enumeración parcial -> consistencia local -> enum parcial...

## Forward Checking

Verificamos las restricciones antes de instanciar las variables.

### Ejemplo

![[Pasted image 20211116110416.png]]

Empezamos con $100*100*100$ combinaciones posibles, y despues de la ver de consistencia local tenemos $4*4*4$ combinaciones posibles.

Ahora que no se pueden eliminar más valores, empezamos a enumerar. 

![[Pasted image 20211116110603.png]]

---

- Son completas (de enumeración)
- Uso Activo de restricciones (de consistencia local)
- Necesidad de balance enumeración/verificación de consistencia. Una buena idea es hacer, enumeración de una var, verificar consistencia de hartas, susecivamente.
- Complejas heurísticas incluyendo saltos en el árbol de búsqueda,
	- Full Lookahead
	- Intelligent Backtracking
	- ...

