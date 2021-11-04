Nos interesa determinar la mejor union de subconjuntos que contenga todos los elementos del universo.

## Ejercicio ejemplo :

![[Pasted image 20210920205509.png]]

Hay 20 zonas, y en cada circulo se instalan los servicios.
El universo son los 20 elementos.

![[Pasted image 20210920205904.png]]

![[Pasted image 20210920205832.png]]

Queremos minimizar la cantidad de sercvicios instalados, por lo que :

![[Pasted image 20210920210007.png]]

Las restricciones se extraen del mapa y se realizan para las 20 zonas, por lo que si para la zona 1 solo esta el servicio $x_1$, se genera la primera restriccion. Esta debe ser $\geq 1$ ya que debe tener al menos un servicio cerca.

Ahora si se asocia un costo a la instalacion de cada uno, podemos intentar minimizar los costos. Con los costos $c_i$ para la inst de cada servicio:

![[Pasted image 20210920210342.png]]

- Las restricciones se mantienen igual que antes

[[Qin2]]