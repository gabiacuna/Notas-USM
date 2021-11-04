# Kahoot Miércoles
1. La virtualización es ejecutar mas de un so de forma concurrente en un mismo computador. Es muy parecido a emular para jugar juegos viejos. Se conoce a host el so principal y guest a el que se descarga. 
2. En una virtualización de modo dual, el modo kernel del guest se ejecuta mediante el modo usuario del host. -> Ambos modos (usuario y kernel) del guest se ejecutan en modo usuario del host.
3. Son beneficios de la virtualización:
	1. Gestión de estados (Congelar, suspender, guardar estados, etc).
	2. Ahorro de hw. No necesito comprar dos maquinas para tener 2 so.
4. Existen procesos que no son hechos por el usuario. Tmb hay procesos del so, como llamadas al sistema.
5. Son parte de las componentes de un proceso:
	1. Stack
	2. Heap
	3. Datos
	4. Código
6. Las variables globales se almacenan en los datos. 
	- En el codigo se guardan las instrucciones a ejecutar.
	- En el stack, estan los datos y variables temporales.
	- En el heap estan los datos en tiempo de ejecución.
7. Cuando se llama a una función se guarda la direccion de retorno en el stack. 
8. No es un estado de un proceso:
	1. En camino.
	- Si lo son:
		- Nuevo
		- Listo (es cagado en memoria)
		- En espera
		- En ejecución (cuando esta en la cpu)
			- Si lo interrumpen vuelve a listo
			- Si hace una E/S va al estado de espera
			- Si termina, finaliza
		- Finalizado 
		- ![[Pasted image 20211012092938.png]]
> cuando se inicia el compu estan todos los procesos en la memoria principal, despues saltan a la RAM y ahí estan listos. Cuando el itinerador (entidad que se encarga de ver que proceso se va a ejecutar ahora) ve un proceso en la RAM y lo pasa a la CPU. 

> Memoria principal, es el disco todo antes de ser cargado en la RAM. 

9. El itinerador de largo plazo controla el grado de multiprogramación. Por que es quien gestiona cuanta carga se le da al itinerador de corto plazo.
10. El rendimiento del compu no se ve beneficiado si solo se ejecutan procesos CPU. Por que tiene que haber un equilibrio entre procesos CPU y procesos E/S, para poder ocuparlos ambos al mismo tiempo, si tengo puros procesos CPU la terminaré sobrecargando.

## Función fork

![[Pasted image 20211012094159.png]]
## Ej 1 - dibujar la jerarquia de procesos
![[Pasted image 20211012094240.png]]
En C los for se ejecutan:
1. x = 0
2. x < 4
3. body del for
4. x++
5. x < 4
6. body
7. x++
8. ....

P0 : Proceso inicial, del que se parte.
Cuando se llega al if (fork() != 0), se duplica el proceso. fork va a retornar el id de p1 que es distinta de 0.
![[Pasted image 20211013125619.png]]

ahora seguimos con la ejecución de P0, P1 queda pendiente. Se entra al segundo for. ahora se crea el fork del p0 -> p2, se retorna el id de p2, por lo que el if es fake. Se pasa a la siguiente iteración y se crea p3 a partir de p0. cuando termina el for, se acaba el proceso padre (p0), pk se llega al final del código:
![[Pasted image 20211013125830.png]]
Pero p1, p2 y p3 no han terminado.
p2 se creo en el segundo  fork, y lo ve como un 0, por lo que entra al break y termina.
P3 tmb se creo en el segundo fork y lo ve como un 0, por lo que termina el proceso.

> un break termina la ejecución de un bucle.

Ahora se ejecuta un fork desde p1, por lo que se crea un proceso desde ahí. Luego entra al segundo fork y se crean 2 procesos, p5 y p6.

![[Pasted image 20211013130852.png]]

P5 y p6 se comportan igual que p2 y p3. Ahora para p4, ocurre lo mismo que p1

![[Pasted image 20211013131048.png]]

Ahora falta que p10 ejecute el for 2:

![[Pasted image 20211013131122.png]]

Ahora esta listaaa c:

