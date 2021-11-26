# Problemas de Satisfaccioón de Restricciones.

Variables, _Dominios_ y Restricciones

Originalmente los problemas se representaban mediante grafos, y eran binarios. Donde a lo más hay 2 variables interviniendo en las restricciones.

Importa el orden, en el calculo, $A \neq B$ es distinto de $B \neq A$.

Vamos a repetir una iteración en basea la Enumeración de valores y la verificación de consistencia local.

## Técnicas

- [[Enumeración de valores]]
- [[Verificación de consistencia local]]
- [[Híbridas]]

Una vez que se tiene una solcucion, se agrega una cota a la F.O. Hasta que no se pueda seguir avanzando

# Seleccion de Variables y de Valores

La forma en la que uno los escoge, tienen una importancia relevante en la eficiencia de la busqueda.

- [[Criterio de selección de variables]]
- [[Criterio de selección de valores]]

### Ejemplo

![[Pasted image 20211116111617.png]]

![[Pasted image 20211116111647.png]]

La primera solución después de $4*100*100$ intentos fallidos.

Si ahora la selección de valores se hace de _mayor a menor_ entonces se llega a la primera sol , despues del $92*100*100$ intentos fallidos.

Tablita para el caso de mayor a menor:

![[Pasted image 20211116111920.png]]

