## Micro Kernel

![[Pasted image 20211006153051.png]]

Intenta mover todos los grupos de servicios al modo usuario, para que no sea necesario ejecuratlos con privilegio de kernel.

No se dejan con privilegios para ser ejecutados.

![[Pasted image 20211006153101.png]]

Grupos de servicios más criticos se dejan en el kernel, y el resto que no necesitan del SO para ser ejecutados, se dejan fuera, con permisos de usuario

![[Pasted image 20211006153113.png]]

Los mecanismosde mensajeria se implementan a travez de llamadas al sistema, por lo que añadir un mecanismo de comuinicacion extra va a generar mas eventos de interrupcion solo para comunicar entre dois servicios.