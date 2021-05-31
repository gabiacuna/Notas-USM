### Falla en Implementación de Sistema de Laboratorio Clínico

- Caso sobre laboratorio clinico para caso 2 [[osi]]

Autor: Manuel Ahumada Contreras.
Fuente: [link](https://lc-ip81.inf.utfsm.cl/wiki/index.php/Falla_en_Implementaci%C3%B3n_de_Sistema_de_Laboratorio_Cl%C3%ADnico)

Si para gestion de un laboratorio clinico, en un hospital regional en el sur de Chile.

> Objetivo principal del laboratorio clinico es ==gestionar todos los flujos que contempla el análisis de muestras biológicas== de los pacientes para asegurar la ==entrega de resultados de pruebas que permitan realizar un diagnóstico confiable== por los profesionales clínicos que atienden paciente en el Hospital Regional.

Flujos principales que controla el sistema:
- ingreso de ordenes del laboratorio
- gestion de datos demográficos de pacientes
- gestion de agenda para tomas de muestra
- gestion del proceso de extraccion de muestras biológicas
- seguimiento de muestras
- procesamiento de muestra en equipamiento clinico para la obtencion de resultados
- emicion del reporte de resultados de cada paciente

> La presicion del sistema es crucial, ya que un error le puede costar la vida a un paciente.

#### Flujo de laboratorio clínico
##### Datos que manejaba el sistema:
* Toda la info demográfoca del paciente
	* RUN, Nombre completo, fecha de nacimiento, sexo, direccion, etc
* historia clinica completa a nivel de resultados de lab de cada paciente
	* registros de las tomas de muestras
	* registros de la gestion de las muestras
	* registros de emicion de los resultados clinicos con la firma electronica correspondiente al profesional de la salud (técnologo médico)
* Respecto al establecimiento donde es implementado
	* procedencias de donde provienen las solicitudes de los examenes
	* registro de medicos responsables de las solicitudes
	* registros de todos los profecionales que interactuan con la aplicacion dentro del laboratorio

##### Procesamiento de Datos
1. Ingreso de una solicitud de toma de examenes de un paciente
2. Segun los examenes que fueron solicitados se ejecutta un algoritmo de reconocimiento de parámetros según la configuracion de las prestaciones que fue realizada en el sistema del laboratorio. 
3. Con el resultado de 2. el sistema entrega ak profecional de la toma de muestras (flebotomista) la identificacion de muestras que se debe obtener del paciente, en que tipo de contenedor colectar y ademas se emiten las etiquetas de código de barra con la info de cada paciente ( para no perder las muestras ).
4. Las muestras son enviadas y luego recepcionadas por el lab
5. Las muestras son derivadas a las distintas secciones analíticas dentro del laboratorio clinico siguiendo reglas dadas por lso jefes del lab.

Composicion del laboratorio:
* equipamiento clínico para el procesamiento de muestras -> identifican que examenes realizar a las muestras consultando a un sistema externo, en este caso el SI del lab

La integracion entre el sistema del lab y el equipo clínico es Bidireccional.

##### Informacion generada por el sistema

* *Registros clínicos del paciente*: gestiona los datos demográficos del paciente,se puede saber cuando un paciente fue creado en el sistema, cuando fue modificado y por quien es el responsable. Tambien se almacenan datos de pacientes que no poseen identificador, como recien nacidos, urgencias, examenes  anonimos como el del VIH etc
* *Registro de las muestras*: se puede saber la fecha de ingreso de las muestras, fecha y responsable de la extracción de cada muestra, fecha y responsable del envío de las muestras al laboratorio, fecha y responsable del procesamiento de las muestras y por ultimo el desecho de las muestras una vez que son obtenidos los resultados.
* *Registro de resultados*: se registra cada resultado emitido por los analizadores identif. claramente el origen y la fecha en la que fueron transmitidos. Los resultados pueden ser **numericos, cualitativos (positivo  o negativo), o con comentarios e interpretaciones**. Los numericos se comparan con rangos de referencia. 
* *Emision de reporte de resultados*: emite resultados siguienso las normativas vigentes a nivel nacional para laboratorios clinicos acreditados segunla la ley del minsal
* *Registro de Auditorias*: Es sist con toda la info emite indcadotres de calidad con los que el lab ve el nivel de efectividad de sus procesos. 

---
#### Identificacion del fallo del SI

Para implmentar el sistema se debe realizar un blackout del sistema saliente.

* **Personas**:
	* No se expucieron todos los requerimientos necesarios del SI.
	* No se pudo capacitar al personal para usar el sistema.
	* Resistencia al cambio, debido a la automatizacion de tareas manuales.
	* Falta de informacion de la toma de muestras (contenedores, fechas, horas, lugares, etc)
* **Procesos**:
	* En el periodo de implementacion no se dieron instancias para revisar la informacion que se le estaba proporcionando al sistema, todo fue trasbajado de localmente sin recibir feedback de las diferentes areas en las que se estaba implementando el sistema.
	* Solo se realizaron pruebas al sistema en un ambiente controlado. No se previnieron muchos problemas.
	* No se realizo ninguna marcha blanca con muestras reales. Tampoco se verifico el desempeño de las integraciones. 
* **Datos**:
	* Problemas de configuracion de decimales, '1.2' se entregaba como '12'. Arrojaba falsos positivos por esta razón.
	* Los analizadores no fueron configurados correctamente para los paremetros de transmicion. Por esto habia que insertar los datos manualmente y la marcha blanca fue *insostenible*.
	* No estaban configurados en el sistema todos los profesionales que iban a interactuar con el.
* **Red de comunicación**:
	* Algunos analizadores utilizan como canal de comunicacion el protocolo TCP/IP. Con el gran flujo de datos en la puesta en marcha se detectó latencia y guna gran perdida de paquetes.
*  **Software**:
	*  Por el gran flujo de pacientes es necesario un sistema muy rápido.