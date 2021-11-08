# Modo dual de Ejecución
![[Pasted image 20211008012105.png]]
 Modo kernel es el modo de sistema operativo, y requiere soporte de hardware, que se llama bit de modo.
 La mayoría de los programas tienen permisos tipo usuario, pero llamadas a sistema requieren modo so.
 
 ![[Pasted image 20211008012234.png]]

Cuando se corre una instruccion, se revisa si se tienen los permisos correspondientes, y si los tiene, se ejecuta.

usuario -> kernel
![[Pasted image 20211008012257.png]]

Cuando se producen estis eventos, se entrega el control de la cpu al so. 
![[Pasted image 20211008013257.png]]
![[Pasted image 20211008013304.png]]


![[Pasted image 20211006122057.png]]

![[Pasted image 20211006122110.png]]

![[Pasted image 20211006122125.png]]

Se implementa en hardware, es un bit, 0 para kernel, 1 para tipo usuario. Este bit se valida para cada ejecución de instrucciones.

El cambio de modo de usuario a kernel es el mas comun, y ocurre cuando se realizan las interrupciones.

![[Pasted image 20211006122340.png]]

Esta figura puede servir para las interrupciuones sincronas.

![[Pasted image 20211006122416.png]]

![[Pasted image 20211006122514.png]]
![[Pasted image 20211006122532.png]]

Upcall : Es una forma del sistema de informar siertos eventos