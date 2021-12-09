# Variables de Condición

> Permite que una hebra espere eficientemente que ocurra un cambio en un estado compartido que está protegido por un lock.
> **Siempre** esta asociada a un lock.

### Ejemplo

En el problema anterior (Ejemplo 2 en [[Locks]]), en vez de producir un error al momento de intentar sacar un elemento de la cola vacı́a, es mejor que las hebras esperen que la cola tenga un ı́tem.

---

## Tiene tres métodos:
- `wait(Lock *lock)`
- `signal()`
- `broadcast()`

1. `wait(Lock *lock)`
	- Atómicamente libera el lock.
	- Suspende la ejecución de la hebra que lo invoca.
	- La hebra se va a una cola de espera asociada a la variable.
	- Cuando despierta, adquiere el lock antes de retornar el wait.
2. Para mover las hebras desde la cola de espera hasta la cola ready:
	- `signal()` : solo una hebra.
	- `broadcast()` : Todas las hebras. 

![[Pasted image 20211130154724.png]]



---
### Ejemplos para los metodos.

![[Pasted image 20211129182700.png]]
Wait **siempre** se ejecuta dentro del while, por lo que espero hasta que llegue la hebra que se quiere ejecutar.

![[Pasted image 20211129182727.png]]

---

- Una variable de condición **no tiene memoria**.
- Solo tiene una cola asociada.
- `wait()` siempre se ejecuta:
	- Reteniendo un lock.
	- Desde el interior de un loop.
- Una hebra despertada por `signal()` o `broadcast()` no se ejecuta
inmediatamente. Simplemente _es dejada en la cola ready_.

Podemos dar una mejor solución al Ejemplo 2 en [[Locks]])
![[Pasted image 20211129183947.png]]

Ahora Mantenemos el candado, agregamos 2 variables de condición (CV), una para agregar los elementos y otra para quitarlos. Ahora varía el insert, lock.aquire, el while se ejecuta hasta que la cola este llena, y dentro de el se revisa que esta pasando en el otro metodo. (flechitas rojas de comunicación cruzada, cuando se agregan y quitan elementos de la cola). 

![[Pasted image 20211129184253.png]]
