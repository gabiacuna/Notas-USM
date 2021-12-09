# Semaforos 

- Es una variable entera
- Se tienen 2 operaciones atomicas.
	- `wait()` ![[Pasted image 20211129194944.png]]
	- `signal()` ![[Pasted image 20211129195011.png]]
- So’s modernos diferencian dos tipos:
	- **Contadores**: Definido en un dominio no restringido.
	- **Binarios**: Valor 0 o 1. Conocidos como Mutex.
- Mutex generalmente protege la sección crı́tica.
- El problema es que presentan _busy waiting_.
- Al menos no producen cambios de contexto innecesarios.
- Se les conoce como **spin locks**.

> Para evitar el _busy waiting_, se modifican los semáforos.
> A cada semáforo se le asigna una cola de espera, donde se definen 2 operaciones.
> 1. **Block** : Lleva al proceso a la cola de espera.
> 2. **WakeUp** : Lleva al proceso a la cola ready.
> En vez de esperar se bloquean.

## Usos Incorrectos

- signal(mutex) ..... wait(mutex)
- wait(mutex) ....... wait(mutex)
- Omitir un wait(mutex) y/o un signal(mutex).

-> Estos errores pueden llevar a [[deadlock]] y/o starvation.

## Ejemplo, Cola delimitada

![[Pasted image 20211130124503.png]]

![[Pasted image 20211130124513.png]]