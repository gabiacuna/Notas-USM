# Locks

- Proporcionan exclusión mutua.
- Si una hebra retiene un lock, **ninguna más puede tomarlo**.
- Tiene dos métodos
	- `acquiure()`
		- Espera hasta que lock esté FREE.
		- Cambia automáticamente a BUSY.
		- Varias hebras esperando: _A lo más una tiene éxito_.
	- `release()`
		- Lock queda en estado FREE.
		- acquire() pendientes: A lo más una tiene éxito.
- Y 2 estados
	- BUSY
	- FREE

## Ejemplo, para el problema del ron.

- Definimos un `Lock lock;`
- La idea es proteger la sección crítica.
```c
lock.acquire();
if( ron == 0){
	ron++;
}
lock.release();
```

- Esta solución cumple con:
	- Exclusión mutua: A lo más una hebra retiene el lock.
	- Progreso: Si nadie lo retiene y se solicita, se obtiene.
	- Espera acotada: El tiempo de espera queda acotado.
- Ojo: No existe orden de asignación del lock.

## Funciones:

![[Pasted image 20211130154407.png]]

![[Pasted image 20211130154447.png]]
Lo entremedio es lo protegido, a lo que solo puede entrar una hebra a la vez.
## Ejemplo, Problema cola delimitada.

- Utilizaremos [[hebras]] para resolverlo.
- Cada **objeto compartido** es una instancia de una clase.
- Se definen sus estados y métodos que operan sobre éste.
- Los estados incluyen variables (int, float, etc. ) y de sioncronización.

![[Pasted image 20211129154740.png]]

- Total de elementos insertado es `nextEmpty`.
- Total de elementos removidos es `front`.
- front ≤ nextEmpty.
- Elementos en la cola: `nextEmpty - front`.

![[Pasted image 20211129180716.png]]

![[Pasted image 20211129180737.png]]

![[Pasted image 20211129181938.png]]

![[Pasted image 20211129181951.png]]

![[Pasted image 20211129182000.png]]