# Técnicas de consistencia local

Es la base de la programación con restricciones.

Son 4:
1. Nodo
2. Arco
3. Camino
4. Casos Especiales

## Consistencia de Nodo

- Veerifica que los valores del dominio de las variables cumplan con todas las restricciones de aridad 1.
- Un nodo puede ser consistente o inconsistente
- CSP consistente en los nodos : todos los nodos son consistentes
- Valores que no satisfacen las restricciones deberían ser _eliminados._

### Ejemplo

![[Pasted image 20211116102616.png]]

En $D_A$ los 3 primeros si satisfacen la condición, pero no el $4 y 5$, por lo tanto el nodo A es inconsistente. $D_B$ cumple con sus condiciones por lo que es consistente. Y el nodo C no tiene restricciones por lo que es consistente. 

Ya que el grafo tiene _un nodo inconsistente_, se determina que el problema es inconsistente. 

- Esto es muy básico, se aplica a restricciones de grado 1.

## Consistencia de Arco

- Verifica que los valores del dominio de una variable sean compatibles con los valores del domino de las variables relacionadas en _restricciones de ariedad 2_.
- Un arco puede ser consistente o inconsistente.
- CSP consistente en los arcos : todos los arcos son consistentes.
- Valores que no satisfacen las restricciones deberían ser eliminados.

### Ejemplo

![[Pasted image 20211116103107.png]]

Primero analisaremos si el arco de A -> B es consistente. Si encontramos al menos una alternativa que soporte a un valor, entonces este valor es posible para su variable. En A, el primer Valor es 1, si se compara con el primer valor de B, no sirve, pero con el segundo si, así que este si es un valor posible. Si todos los valores son posibles para el nodo A (llendo hacia el nodo B), entonces se dice que todos los valores para el nodo A tienen soporte, son posibles para comparar con el nodo B. Por lo que el arco (A B) es consistente.

El arco (A C) se cae por que en A=5 no se puede cumplir la restricción.

## Consistencia de Camino

- Verifica que los valores del dominio de una variable sean compatibles con los valores del domino de todas las variables relacionadas a través de un camino.
- Un camino puede ser consistente o incostistente, y un CSP es consistente en caminos si todos los caminos son consistentes.
- Valores que no satisfacen las restricciones deberán ser eliminados.

### Ejemplo

![[Pasted image 20211116104014.png]]

El recorrido puede ser:
- valor 1 es posible para A?
	- Revisamos A->B->C
	- Como B puede ser 2, A B es factible. Como C puede ser 3 entonces si es consistente. 

La consistencia de caminos es mas potente  que la consistencia de arcos. Entrega más informacion, pero la aplicación es más cara.

### Algoritmos de verificación de consistencia de arcos

```
Funcion REVISAR(c(xi , xj)): boolean
	Inicio
		RETORNAR ← F;
		Para cada v ∈ Dxi hacer
			Si 6 ∃ w ∈ Dxj tal que c(v, w) = V entonces
				Dxi ← Dxi\v;
				RETORNAR ← V;
			fin-si
		fin-hacer
	Fin
```

Apenas se encuentra un valor con soporte, se retorna true. Entrega resultado falso, si todos los valores del dominio de la primera variable, no tienen soporte con ningun valor de la segunda varibale.

```
Procedimiento AC-1;
    Inicio
        Q ← {(xi , xj) | (xi , xj) ∈ arcs(G), xi 6= xj};
        Repetir
            cambio ← F;
            Para cada (xi , xj) ∈ Q hacer
                cambio ← cambio ∨ REVISAR((xi , xj));
            Fin-hacer
        Hasta ¬cambio
    Fin
```

Algos y su complejidad:

![[Pasted image 20211116105352.png]]

# Especialización de Algoritmos de Verificación de Consistencia de Arcos.

## Propagación de bordes

![[Pasted image 20211116105426.png]]

no es necesario revisar todos los valores posibles.

### Ejemplo

![[Pasted image 20211116105705.png]]

- Analiza solo los bordes evitrando recorrer cada valor de el domino.
- Ampliamente utilizado en dominios ordenados.

## Disyunción constructiva

![[Pasted image 20211116105902.png]]

### Ejemplo

![[Pasted image 20211116105918.png]]

No se que lado de la restriccion voy a utilizar. así que se analiza cada componente de la disyunción. Entonces puedo acotar los dominios. 

- Uso activo de los componentes de disyuncion.
- No hay eleccion a priori entre componentes.

---

# Resumen
![[Pasted image 20211116110109.png]]

La de nodos se ocupa como paso previo a la consistencia de arcos.