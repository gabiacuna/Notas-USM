```
title HU 3 Mostrar los resultados de la busqueda

actor Jefa del Archivo
boundary View
control Control


entity Paginas Web

Jefa del Archivo->View:Mensaje Sincrono, Apretar botón de busqueda

activate View

View->Control:Realizar solicitud de busqueda
activate Control
Control->Paginas Web:Realizar busqueda
activate Paginas Web
Control<-Paginas Web:Resultado busqueda
deactivate Paginas Web


loop i < cantResultados
activate View
View<-Control:mostrarResultado(i);
deactivate View
end

deactivate Control

deactivate View
```