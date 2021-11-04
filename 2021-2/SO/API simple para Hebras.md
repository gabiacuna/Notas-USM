![[Pasted image 20211103124717.png]]

La mayoría tienen practicamente las mismas funciones. Hay que descargar las bibliotecas `sthread.c` y `sthread.h`.

# Funciones: 
![[Pasted image 20211103124827.png]]
![[Pasted image 20211103124838.png]]

## Ejemplo
El static es para evitar que las hebras se modifiquen entre ellas.  

```c
/*
* threadHello.C -- Simple multi-threaded program.
* 
* Compile with
*	> gcc -g -Wall -Werror -D_POSIX_THREAD_SEMANTICS threadHello.c -C-0
threadHello.o
*	> gcc -g -Wall -Werror -D_POSIX_THREAD_SEMANTICS sthread.c -C-o sthread.o
*	> gcc - pthread threadHello.o sthread.0 -0 threadHello
* Run with
* 	> ./threadHello
*/

#include <stdio.h>
#include "sthread.h"

static void go{int n);

#define NTHREADS 10
static sthread_t threads [NTHREADS) ;

int main(int argc, char **argv)
{
	int ii;
	for(ii = 0; ii < NTHREADS; ii++){
		sthread_create(&(threads (ii)), &go, ii);
	}
	for(ii = 0; ii < NTHREADS; ii++) {
		long ret = sthread_join(threads[ii]);
		printf("Thread %d returned %ld\n", ii, ret);
	}
	printf("Main thread done. \n");
	return 0;
}
void go(int n)
{
	printf("Hello from thread %d\n", n);
	sthread_exit(100 + n);
	// Not reached
}
```

En el for se crean las hebras. La hebra main espera la ejecución de todas las hebras. Con el segundo `join`.

Una posible salida:

![[Pasted image 20211103125729.png]]

El programa no es determinista, por lo que si volvemos a ejecutar, puede ser que se produzca la misma salida o no. Lo que nunca va a orcurrir, es que se muestre un msg de termino antes que uno de inicio. Si cambia el orden de las hebras ya que la ejecucion de estas depende del itinerador.

- El Maximo numero de threads corriendo al mismo tiempo, depende de la arquitectura. Por ejemplo si se tienen 8 nucleos logicos, entonces se tienen las 8 hebras al mismo tiempo.
- El minimo, es una. Si es 0, el proceso no se está ejecutando. 

