# Constraint satisfaction problems
Poseen.
* Parametros : Lo conocido, no se puede cambiar.
* Variables : Lo desconocido, si se puede modificar.
* Restricciones : Relaciones entre variables y parametros

Podemos definir:
- una solucion : Asignacion de valores a las variables
- una solucion factible : Una solucion que satisface todas las variables.

Un CSP puede ser:
- Tener Soluciones factibles : Si existe al menos una solucion factible.
- No contar con soluciones factibles.

Resolver un CSP significa buscar una o todas las soluciones factibles. O demostrar que no existen soluciones factibles.

# Constraint Satisfaction Optimization Problem

Consiste de :
- CSP : Variebles, parametros y restricciones.
- Funciones objetivo : Funciones a ser optimizadas, satisfaciendo todas las constantes.

Ahora podemos tener una **Solucion optima**, es factible y mejor o igual que todas las otras soluciones.

Se puede :
- Tener soluciones factibles no limitadas (crecen indefinidamente)
- Tener una unica solucion optima.
- Tener multiples soluciones optimas. (Cuando son todas igualmente buenas)

## Tecnicas de Solución

Existen 2 enfoques:
1. Técnicas completas o globales, que buscan la mejor de todas las soluciónes, más seguro pero más costoso.
2. Técnicas incompletas o locales, buscan por la mejor solucion entre un grupo de soluciones.

Son tecnicas complementarias y se pueden ocupar ambas.

[[Q3]]