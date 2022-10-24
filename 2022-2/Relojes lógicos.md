En algunos casos no es necesario acordar una hora actual
↪ Si dos procesos no interactúan, no es necesario que sus relojes estén sincronizados.
↪ Puede que sea suficiente conocer el orden en el que ocurren los eventos.
↪ Los utilizamos para mantener el **orden total entre eventos**. Pero no hay relación con el tiempo físico real.

Se define una prioridad de eventos de forma aleatoria.

> Evento, es la ocurrencia de una sola acción que lleva a cabo un proceso mientras se ejecuta.

> El evento a "sucede-antes" que el evento b, y es representado de forma : $a \rightarrow b$. Esta es una relación transitiva!!!.

## Relojes lógicos de Lamport

Se ponen de acuerdo con los tiempos que llevan los mensajes, para mantener la consistencia.
![[Pasted image 20221023165745.png]]
En este caso, cuando $m_3$ llega a $P_2$, su reloj se actualizaría de $56 \rightarrow 61$ y luego se ajustaría el reloj de $P_1$ a 70, ya que $m_4$ es mandado en el tiempo 69 de $P_2$.

> Los contadores se actualizan sumando 1 al tiempo en el que fue mandado el msg.

⛔Estos relojes no muestran la causalidad entre los mensajes (el reloj no nos puede decir si un proceso ocurre antes que otro).

## Relojes vectoriales

> Para una sistema de N procesos, es una matriz de N enteros.

A cada evento se le asigna un nombre único y se hace un seguimiento de las historias causales.

$$V[i] \Rightarrow [a_i ... a_n], \text{, n procesos}$$

$V_i[i]$ es el numero de eventos que $p_i$ tiene marca de tiempo.
$V_i[j]$ es el num de eventos que jan ocurrido en $p_j$ y potencialmente han afectado a p_i.

Cada proceso mantiene su reloj vectorial $V_i$ y es actualizado cada vez que se recibe un mensaje.

> ### Actualización de un reloj vectorial
> Se compara cada elemento del reloj propio, con el que viene en el msg. Se elige el numero mayor, en caso de que sea el del reloj propio y se le suma 1. En caso de que sea el que viene en el msg, se copia en el espacio correspondiente.
> Ex, se manda un mensaje de $P_2$ a $P_3$.
> ![[Pasted image 20221023172428.png]]

### Determinar causalidad

Solo podemos decir que $P_1$ y $P_2$ son causales, ssi $P_a[i] > P_2[i] \forall i$ o $<$, pero debe cumplirse la misma regla (estricta) para todos los elementos del reloj vectorial de ambos procesos.

|$P_1$ (1, 2, 3) | $P_2$ (0,1,1) | Causales |
|-|-|-|
|$P_1$ (1, 3, 2) | $P_2$ (4,1,1) | Concurrentes |

Estos relojes tb se ocupan para *versionamiento de datos*, de esta forma modificaciones son propagadas de forma asíncrona.

