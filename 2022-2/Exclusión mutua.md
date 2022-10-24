Solo un candidato puede trabajar sobre un recurso a la vez. Pero los procesos quieren acceder simultáneamente al recurso.

Soluciones:

1. **Soluciones token-ring**: Pasar un mensaje especial entre procesos (token) y solo un proceso lo tiene a la vez.
2. **Enfoque basado en permisos**:  Un procesos que espera acceder al recurso primero requiere el permiso de los otros procesos.

Protocolo a nivel de aplicación para ejecutar una sección critica:
- `enter()`
- `resourceAccess()`
- `exit()`

Requisitos:
1. 1 proceso escribe a la vez (*seguridad*).
2. Tiene que terminar de escribir en algún momento, las solicitudes tienen éxito (*vitalidad*)
3.  El orden en el que me asigna un recurso es cuando lo pedí, solicitud respondida en orden (*ordering*). 🌠 Esta es opcional 🌠.

## Algoritmo centralizado

- 1 proceso (coordinador) recibe todas las peticiones y va asignando. Esto simula un sistema de un procesador.
- Mantenemos el orden, solo 1 persona escribe.
- No podemos asegurar que un proceso termine.

Pro: 
- Es simple.
- Es justo, concede acceso por orden de solicitud.
- Sin inanición, ni punto muerto.
Cons: 
- Si se cae el coordinador, muere todo (punto único de fallo). 
- Coordinador puede hacer el cuello de botella.
- Un proceso puede responder o no, si no responde deja al otro proceso esperando. Puede haber confusion entre no responder y permiso denegado.

![[Pasted image 20221023195740.png]]

### Algoritmo distribuido

Se supone que *el envío de mensajes es confiable*.
- Cada proceso tiene su timer (lógico) y lo manda en un mensaje a todos los procesos y si mismo. Cuando recibe un OK de todos escribo.
- Problema de N puntos de fallo y con multitask.
![[Pasted image 20221023200214.png]]

Cuando un proceso recibe un msg de solicitud:
- Si no esta accediendo al recurso y no quiere hacerlo, envía OK.
- Si el receptor ya esta accediendo al recurso, no responde. Pone en cola la solicitud, y cuando termina envía OK a todos los procesos en la cola.
- Si el receptor quiere acceder al recurso, compara el timestamp del msg entrante con la que contiene el msg que envió a todos y el más bajo gana.

Pros:
- Sin pto muerto.
- Sin inanición.
- Numero de mensajes $2\cdot (N-1)$.
Cons:
- N puntos de falla.
- Comunicación de Multicast o comunicación de grupo.

### Algoritmo distribuido usando relojes de Lamport
![[Pasted image 20221023211634.png]]

## Algotirmo de red en anillo (token-ring)

- Se construye una red superpuesta en forma de anillo lógico. Nuevamente solo escribe quien tiene el token. 
- No existe el orden de petición, solo orden en el que se pasa el token.
- Si falla uno mata todo.
|![[Pasted image 20221023211904.png]]| Cuando el proceso recibe el token, revisa si necesita acceso al recurso compartido, y lo pasa (en caso de necesitarlo, usa el recurso y desp para el token). |
|-|-|

Peor caso: Espere que todos los demás procesos que usan el recurso antes de recibir el token.

- Sin inanición.
- Detectar fallas es difícil.
- Tiempo ilimitado entre entregar el token (se puede quedar estancado).

### Algoritmo de votación

Cada proceso puede votar por solo un recurso, necesitamos overlap entre votantes!. 
Para $N$ nodos necesito $\sqrt{N}$.