> Buscamos un algoritmo que escoja un único proceso para cumplir con un rol en particular.

Como nos ponemos de acuerdo? a los SD no les gusta la democracia, eligen algoritmos más autoritarios (son más rápidos).

> El obj de un algo de elección es asegurar que cuando una elección empieza, concluye con todos los procesos estando de acuerdo respecto a quien es el nuevo coordinador.

## Bully Algorithm

El coordinador elegido es quien tiene el id más alto, el proceso comienza cuando se cae el coordinador y el nodo que primero nota la falla es quien empieza a avisar al resto para comparar ids.
↪$id = \frac{n}{carga}$, n = cantidad de nodos. 

Se necesita un algoritmo de desempate.

**Peor caso** : nodo que nota la falla es el con id más pequeño.

ej:
![[Pasted image 20221025164412.png]]

## Ring based election algorithm

Se recorre un anillo lógico entero, cada proceso conoce a su sucesor. Cuando un proceso nota que el coordinador no esta funcionando, crea un msg de *election* con su id y se lo manda al sucesor.
↪ si el sucesor es menor, se salta al siguiente elemento del anillo.
↪ En cada paso quien envía agrega su id al msg, para ser candidato a coordinador.
Cuando el msg vuelve al nodo inicial, se manda un msg de *coordinador* para informar a todos quien es el nuevo coordinador (el id más alto registrado en la lista).
![[Pasted image 20221025165224.png]]