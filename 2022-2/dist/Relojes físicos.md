## Reloj de hardware

Los compus tienen un circuito para controlar el tiempo (temporizador). 

*Cristal de cuarzo* es el estandar de frecuencia de reloj asequible y estable para microprocesadores.

Cuando se mantiene bajo tensión, el cristal de cuarzo oscila con una frecuencia bien def que depende del tipo de cristal (como se corta y la cantidad de tension).

![[Pasted image 20221023130624.png]]

Se puede ´rogramar un temporizador para tener cierta cantidad de interrupciones por segundo.
-> cada interrupcion se llama un tic de reloj.

## Problemas con los relojes y varias CPU

- Los relojes se desvían.
↪ Es imposible garantizar que los cristales en diferentes computadores funcionen exactamente a la misma frecuencia.
↪ Fenomenos en los que un reloj no funciona exactamente a la misma velocidad que un reloj de referencia.

- Los relojes se desincronizan gradualmente.
↪ **Sesgo del reloj**: dif instantánea entre las lecturas de dos relojes cualesquiera.

- Falta de un tiempo global (zonas horarias, rotaciones al sol....)
↪ No existe un tiempo global absoluto.

> todo esto nos lleva a la dificultad de conocer el **estado** de un programa dist.
> ↪ Queremos marcar con precisión los eventos de marca de tiempo en diferentes nodos para saber en que orden ocurrieron un par de eventos.

💡 **Estado de un proceso incluye los valores de todas las variables dentro de el.**

