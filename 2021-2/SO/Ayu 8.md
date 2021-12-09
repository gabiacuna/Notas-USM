# Kahoot

#deckC2

1. La ejecución de un conjunto de [[hebras]] sin mecanismos de sincronización siempre tendrán el mismo resultado ::: Falso!!! 
2. Una [[condición de carrera]] se produce cuando el comportamiento de un programa ::: Depende del orden de ejecución de sus operaciones.
3. Solo los procesos que involucran [[fork]]() pueden presentar una condición de carrera ::: Falso!!! Tambien se puede con hebrassss
4. ¿ Qué es la Sección Crítica? ::: Seccion de codigo donde se accede al objeto compartido.

En el ejemplo del bar, la seccion critica es el bar, donde se ve si ya hay ron.

5. Solo un proceso entra a la sección crítica. Esta definicion corresponde a .... ::: Exclusión Mutua.
6. Dos hebras pueden retener el mismo lock :::  Falso Los locks se cierran si alguien va a entrar a la zona crítica y si otra quiere entrar no puede, por que esta cerrado
7. No existe orden de asignación del lock ::: Verdadero. 
8. Una hebra ejecutada por `broadcast()` se ejecuta inmediatamente ::: Falso, traspasa a la cola ready.
9. Los métodos de acceso a semáforos son átomicos. ::: True, un método es atómico son aquellos que no pueden ser interrumpidos. Si parte, no se detiene hasta que finalize.
10. Para evitar el busy waiting, los semáforos implementan ... ::: Una cola de espera para cada uno. Busy waiting es cuando los procesos estan esperando mientras consumen CPU.

---

# Materia
## Locks y Variables de Condición

Generalmente van de la mano. Hay escenarios en los que los procesos se ejecutan de Forma concurrente. Y en la mayoría de los casos, estos procesos comparten zonas de memoria, denominados zonas críticas. De modo que no haya resultados inesperados, solo puede entrar un proceso a la vez a dicha zona. Para Asegurar esto, los SO ofrecen distintas herramientas.

# Ejemplo

![[Pasted image 20211130231039.png]]

```cpp
class smashBros{
	private:
		int MAX;
		int players;
		Lock lock;
	public:
		smashBros();
		void play();
		void leave();
};
```

```cpp
void smashBros::play(){
	lock.aqcuire();
	players = players + 1;
	lock.release();
}
```

```cpp
void smashBros::leave(){
	lock.aqcuire();
	players = players - 1;
	lock.release();
}
```

```cpp
smashBros::smashBros(){
	MAX = 4;
	players = 0;
}
```

Se agregaron los locks para que se agregue y quite un jugador a la vez. Aún así, faltan los casos bordes, que son,
1. Cuando un jugador quiere jugar, pero no hay un control disponible.
2. Cuando el moderador quiere sacar a alguien, pero no hay nadie.

Para resolverlos usaremos las variables de condición.

### Cuando el moderador quiere sacar a alguien, pero no hay nadie.

```cpp
class smashBros{
	private:
		int MAX;
		int players;
		Lock lock;
		CV enterGame; // Var de cond!!!
	public:
		smashBros();
		void play();
		void leave();
};
```

```cpp
void smashBros::leave(){
	lock.aqcuire();
	while (players == 0){ // Si se pone un wait es necesario agregar un signal para liberar
		enterGame.wait(&lock); // Se va a quedar esperando forever
	}
	players = players - 1;
	lock.release();
}
```

```cpp
void smashBros::play(){
	lock.aqcuire();
	players = players + 1; // Una vez que se agregue alguien se libera
	enterGame.signal();	// despierta al leave y lo sacan al toque.	
	lock.release();
}
```

### Cuando el jugador desea entrar pero no hay controles disponibles.

```cpp
class smashBros{
	private:
		int MAX;
		int players;
		Lock lock;
		CV enterGame; 
		CV leaveGame; // Var de cond!!!
	public:
		smashBros();
		void play();
		void leave();
};
```

```cpp
void smashBros::play(){
	lock.aqcuire();
	while (players == MAX){	// No podemos agregar jugadores si ya existen 4 en juego!
		leaveGame.wait(&lock);
	}
	players = players + 1; // Una vez que se agregue alguien se libera
	enterGame.signal();	// despierta al leave y lo sacan al toque.	
	lock.release();
}
```

```cpp
void smashBros::leave(){
	lock.aqcuire();
	while (players == 0){ // Si se pone un wait es necesario agregar un signal para liberar
		enterGame.wait(&lock); // Se va a quedar esperando forever
	}
	players = players - 1;
	leaveGame.signal(); // Ahora puede entrar al juego el player que estaba esperando :D
	lock.release();
}
```