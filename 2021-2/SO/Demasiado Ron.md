# Demasiado ron

![[Pasted image 20211117175332.png]]

## Primera Solución

> Cada hebra deja una flag en el bar:

![[Pasted image 20211117180118.png]]

- Seguridad: Nunca se puede comprar más. No se cumple!!!!!
	- ![[Pasted image 20211117180229.png]]
- Vivacidad: Si se requiere ron, alguien compra.

## Segunda Solución

> Se dejan dos notas. Se crean antes de validar:

![[Pasted image 20211117180324.png]]

Ahora dejamos una nota : voy a comprar ron.

- Seguridad OK: Nunca se compra de más.
- Ambas hebras podrı́an dejar sus notas y decidir no comprar.
- Falla con la vivacidad.
- La idea es que si se requiere, al menos una compre.

## Tercera solución

> Al menos una hebra se asegura si se ha comprado o no.

![[Pasted image 20211117180507.png]]

- Funciona correctamente.
- La hebra B no tiene loops. Si termina notaB = 0.
- La solución tiene vivacidad y seguridad pero es:
	- Compleja.
	- Asimétrica: Códigos diferentes.
	- Ineficiente: A produce espera ociosa.
	- Falla ante un reordenamiento de instrucciones.