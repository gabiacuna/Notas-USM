> Es un problema para los procesos escoger un valor luego de que uno o más procesos haya propuesto cual debería ser dicho valor.

ejemplos:![[Pasted image 20221025165739.png]]

Si:
- Tenemos una colección de n procesos, comunicándose por paso de mensajes.
- Se debe llegar a un consenso incluso en la presencia de fallas.
-  Hay fallas bizantinas : nodos pueden mentir o se pueden perder mensajes.
- Un numero f de los n procesos es defectuoso.

### Requerimientos para un algoritmo de consenso.

1. **Terminación**: Eventualmente cada proceso tiene una decisión para una variable.
2. **Agreement**: El valor decidido por todos los procesos no defectuosos es el mismo.
3. **Integridad**: Si los procesos correctos proponen el mismo valor, entonces cada proceso correcto, en su estado decidido ha escogido ese valor. 

## Problema del general bizantino en sistemas síncronos.

![[Pasted image 20221025182412.png]]

- f : Cant de procesos que tienen msg con fallas / pueden fallar.
- n : cantidad de procesos.

Si $n \leq 3\cdot f$, no hay solución.

Hay solución:
![[Pasted image 20221025190827.png]]

---
## Consenso en Sistemas Asíncronos.
- se ha probado que ningún algoritmo puede garantizar un consenso en un sistema asíncrono.
↪ En un sist asíncrono, procesos pueden responder msg en momentos arbitrarios, por lo que un proceso  caído es indistinguible de uno lento.
↪ Si se puede llegar a un consenso, pero es con una probabilidad

Cosas que podemos hacer:
- Enmascarar fallas (almacenamiento persistente, reiniciar un proceso apenas se caiga...)
- Usar un detector de fallas: se tiene un timeout.
- Llegar a un consenso utilizando randomization: induce un elemento de probabilidad al comportamiento del proceso, para que el adversario no pueda ejecutar su estrategia de frustración de forma efectiva.

## Implementando Paxos

Es una familia de protocolos, que provee *consenso distribuido*.



| Pasos del algoritmo: <br>1. Necesita tener un coordinador, a quien se le asigna un `seq_number` que envía a todas las replicas, que promete no tratar con otro coordinador (anterior). <br>2. El coord debe elegir un valor y luego enviar un msg se aceptación del valor. Las replicas deben aceptar el valor y mandar ack. <br> 3. Si la mayoría envía ack, el coordinador hace un broadcast commit. | ![[Pasted image 20221025230719.png]] |
|-|-|

