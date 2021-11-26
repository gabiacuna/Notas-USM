# Técnicas de Enumeración de valores

Se Clasifican en 2:
1. Generate ¬ Test
2. Backtracking

## Generate & Test

- Asigna valor a todas las variables
- Verifica la factibilidad de todas las restricciones
- Enumeración exhaustiva de todas las combinaciones

### Ejemplo

![[Pasted image 20211116100436.png]]

Toma cada variable, toma un valor para cada uno y revisa la factibilidad. Si no se satisfase al menos una condicion, cuenta como infactible y se elimina esa combinacion de variables. **Se comprueban todas las comninaciones posibles**.

- Es muy inestable en su comportamiento

## Backtracking

- Asigna valor a una variable
- Veridica la factibilidad de todas las restricciones que puedan ser evaluadas
- Verifica la factibilidad de todas las restricciones con enumeraciones parciales de las variables

### Ejemplo

![[Pasted image 20211116101049.png]]

Como para $x = 1...4$ no sirve, para esos valores de x se prueba solo una vez. La tabla se acorta muchisimo. Ojito que quedan los resultados inconclusos, quedan evaluaciones parciales, no respuestas

---
## Conclusión sobre las tecnicas de enumeración
- Son tecnicas completas, si existe una solución esta será encontrada.
- Utilización pasiva de las restricciones, solo las uasamos para verificar los valores a porsteriori de la def de variables.
- En general, son impracticables en problemas grandes.
