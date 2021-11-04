# Fork

[GfG](https://www.geeksforgeeks.org/fork-system-call/)

> Es una llamada al sistema, para crear un nuevo proceso, que se llama proceso hijo del proceso original. 

- No recibe parametros
- Retornos:
	- **<0** : La creacion del proceso hijo fue fallida.
	- **0** : Se retorna al nuevo proceso hijo.
	- **>0** : Retornado al padre, el valor es el pid del nuevo hijo creado.

![[Pasted image 20211021170611.png]]