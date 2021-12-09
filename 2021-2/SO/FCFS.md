# FCFS

> La CPU se asigna a la tarea que llegue primero

![[Pasted image 20211108175105.png]]
\* Burst Time es el tiempo de CPU

| | Tiempo de Respuesta |
|---|---|
| P1 | 0  |
| P2 | 24 |
| P3 | 27 |
![[Pasted image 20211108175131.png]]

Si consideramos el tiempo de ejecución,

| | Tiempo de Ejecución|
|--- |--- |
| P1 | 24 |
| P2 | 27 |
| P3 | 30 |

Y el tiempo de ejec promedio sería $\frac{81}{3} = 27$

Ahora si modificamos el orden de entrada de los procesos:

![[Pasted image 20211108175632.png]]

## Convoy Effect

Toda la cola se toma mas tiempo y retrasa, solo por un par de procesos lentos. En este caso, el tiempo de espera promedio es mucho mayor si se ejecuta primero el proceso más grande. 

[Convoy Effect in Operating Systems - GeeksforGeeks](https://www.geeksforgeeks.org/convoy-effect-operating-systems/)