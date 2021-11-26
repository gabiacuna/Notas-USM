# Acceso Sincronizado a Objetos Compartidos

1. Conceptos Básicos
2. Problema : demsiado Ron
3. Herramientas

## Conceptos Básicos

Consideramos un proceso con 2 hebras


- Seccion Crítica : Código donde se accede al objeto compartido
- Toda sol a un problema de este tipo debe cumplir con 3 cosas:
	1. **Exclusión mutua**: Solo 1 entra a la sección crítica. _Propiedad de seguridad_
	2. Progreso : Las solicitudes de acceso deben avanzar.  _Propiedad de vivacidad_
	3. Espera acotada: Si se solicicta entrar, la espera es acotada. _Propiedad de vivacidad_

- Construir la solución es pega del programador
	- Puede llevar a errores y otros problemas

> Problema: [[Demasiado Ron]]