[ppt](https://aula.usm.cl/mod/resource/view.php?id=2541568)

# índice

1. [[Hebras]]
2. [[API simple para Hebras]]
3. [[Implementación]]
4. Aspectos Adicionales

# Aspectos adicionales

![[Pasted image 20211103175605.png]]

* [[Paralelismo]]
* [[Concurrencia]]

## Issues

* Que pasa con [[Fork]]()? Duplica la hebra que lo invoca? todas?

![[Pasted image 20211103180417.png]]

* Que pasa con las [[señales]]?

![[Pasted image 20211103180500.png]]

* Podemos cancelar una hebra antes de que termine?

![[Pasted image 20211103180553.png]]

# Afinidad

Para sacar mayor proceso de una arquitectura, si llevo mi proceso al procesador uno, hay data que se almacena en la cache, y ese proceso sale. Lo ideal sería que volviera al procesador uno. Lo ideal es que vuelvan al procesador donde estuvieron recientemente. 