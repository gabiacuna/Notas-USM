[ppt](https://aula.usm.cl/mod/resource/view.php?id=2470080)

Un sistema operativo es software.
![[Pasted image 20210906171910.png]]

El SO tambien es un proceso que se está ejecutando. Los procesos criticos se encuentran cagados en la RAM. 
 
 -> la capa 0 es el hardware, el usuario no es necesariamente una persona.
 
 ## Definición
 
 ### Que tiene que hacer?
 
 *Depende del punto de vista*
 
  - Para un usuario convencional, facilidad de uso y performance.
  - Sistenmas compartidos deben satisdacer a todos los usuarios.
  - Sistemas móviles ajustados para usabilidad y conservar batería.

El SO permite la gestión de archivos

El SO cumple dos roles fundamentales, de **Árbitro** dado que debe asignar equitativamente los recursos de hardware entre los diferentes programas. Tambien debe aislar a los usuarios y los programas entre sí. Esto es por un seguridad de ejecuciones.

Y segundo, de **Ilusionista** ya que hace como si cada programa tubiera todos los recursos del computador para el. Hace parecer que se tienen Infinitos recursos (en CPU y Memoria principal).

### Objetivo Principal

>Proveer un entorno de ejecución de programas de usuario utilizando una forma conveniente y asignando de forma justa el hardware del computador.
>
>Se deben prevenir errores y gestionar las operaciones E/S. -> el SO debe ser confiable

Desde el punto de vista del usuario, el SO debe ser:

- Confiable
	- el sistema hace lo que debe hacer?
	- este aspecto refleja el cumplimiento
- Seguro
- Portable
- Eficiente
	- Latencia : cuento demora una tarea en completarce
	- Troughtput : cuantas operaciones por unidad de tiempo
	- Overhead : cuanto trabajo extra se realiza
	- Justicia : Para todos los usuarios el sistema es eficiente??
	- Predictibilidad

Estos criterios impactan directamente en el diseño de los SO's modernos.

Cada usuario accede independientemente a los servicios de los SO. Cada llamada a procesos es distinta segun cada SO, por ej la instrucción es distinta para c en linux y windows.

## SO's Modernos

So Tienen foco en el usuario y en el smartphone, como Tablets, Laptops, etc. Dispositivos portatiles. 

> Maquinas virtuales y servidores, empresas que no son de tech gastan mucho en esto

para seguridad se tienen distintos ambientes, uno para desarrollar, otro para hacer pruebas iniciales, otro para hacer pruebas con otras intergraciones y produccion.

organizaciones empezaron a migrar todas sus operaciones de servidores fisicos a servidores virtuales, a la 'nube'.

El so debe trabajar muy coordinadamente con el hardware, ejemplo hiperthreading con los nucleos del cpu -> el SO debe poder trabajar con **hebras**!

### Hebras ?

nos permiten programar procesos en paralelos. en el capitulo 4 programaremos con hebras (simple threads c).

### Caché

Mejora el desempeño del sistema en la ejecucion de ciertos programas. 

> ==Toda esta materia es introductoria y se revisara a lo largo del ramos uwu==

\* Revisar textos guía

[[cap1]]
#SO