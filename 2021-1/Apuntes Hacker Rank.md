para imprimir un float con 2 decimales:
```py
print(format(n, '.2f'))
```

Eliminar todas las instancias de in item en una lista (instancias de word en subsList):
```py
subsList = list(filter(lambda x: x != word, subsList))
```
---
### Clases - OOP ###
[w3schools](https://www.w3schools.com/python/python_classes.asp)
Así se definen:
```py
class MyClass:
    ...
```
Así se crea un objeto de la clase:
```py
p1 = MyClass()
```

>Cada clase tiene dos tipos de variables, variables de ==clase== y de ==instancia== :
>* Las de clase apuntan a la misma variable estatica en todas las instancias de la clase.
>* Las de Instancia tienen distintos valores, que varian en cada instancia de la clase.
>
>\*Recordatorio general oop c:

Los **constructores** al igual que en cualquier oop, crean una instancia de la clase.
-> Una clase puede tener uno o mas constructores, que construyen diferentes versiones del mismo tipo de objeto. (Overloaded constructors -> iguales nombres diferentes parametros.)
```py
def __init__(self, name, age):  
    self.name = name  
    self.age = age
``` 

Los **métodos** funcionan como deberia segun oop, considerando que se deben definir dentro de la clase:

```py
def myfunc(self):  
    print("Hello my name is " + self.name)
}
```

> Recordar los getters y setters, por seguridad :)

El pareemetro **self**, es una _referencia a la instancia actual de la clase_ y se usa para acceder a las variables que prtenecen a la clase. No tiene por que llamarse `self`, solo tiene que ser el primer parametro del método. 

Se pueden modificar las propiedades del objeto así:
```py
p1.age = 40 #Setea la edad de p1
del p1.age #con del se elimina la propiedad
```

Se puede eliminar un objeto:
```py
del p1 #Elimina el objeto p1
```

La definicion de una clase no puede estar vacía, pero en case de ser necesario, se puede usar el `pass`
[[Ejemplo en python]]

---

Para leer *inputs hasta eof* (cuando no se sabe la cantidad de inputs):

```py
from sys import stdin

for line in stdin:
 	line = line.strip()
	...
```
---
#### Herencia ####

Para que la clase `B` herede de la clase `A`, se ve así:
```py
class B(A):
	def __init__(self, data1, data2):
		A.__init__(self, data1) #Se llama la func init de la clase padre.
		self.d2 = data2
	...
```

Si se crea una función \__init__() en la clase hija, se sobreescribe la de la clase padre. Igual esa se puede llamar. Para no usar el nombre de la clase padre, se puede usar la funcion `super()`.