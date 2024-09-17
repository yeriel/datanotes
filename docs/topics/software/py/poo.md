# Programación orientada a objetos

La programación orientada a objetos (POO) es un paradigma de programación que parte del concepto de "objetos" como base, los cuales contienen información en forma de atributos o propiedades y código en forma de métodos.

Los objetos son capaces de interactuar y modificar los valores contenidos en sus atributos (estado) a través de sus métodos (comportamiento). Un ejemplo de objeto puede ser un perro que tiene como:

- Atributos: nombre, color, raza, edad, etc. 
- Métodos: ladrar, caminar, comer, etc.

## Clase
Una clase es una especie de "plantilla" en la que se definen los atributos y métodos predeterminados de un tipo de objeto.

## Objeto
Instancia de una clase. Entidad provista de un conjunto de propiedades o atributos (datos) y de comportamiento o funcionalidad (métodos), los mismos que consecuentemente reaccionan a eventos. Se corresponden con los objetos reales del mundo que nos rodea.

## Método
Algoritmo asociado a un objeto (o a una clase de objetos), cuya ejecución se desencadena tras la recepción de un "mensaje". Desde el punto de vista del comportamiento, es lo que el objeto puede hacer. Un método puede producir un cambio en las propiedades del objeto, o la generación de un "evento"

```python
#Clase
class Dog:
    def __init__(self,name,age):
        self.name = name
        self.age = age
    #Método
    def bark(self)
        return f'{self.name} is bark'

#Objeto
dog_1 = Dog('wolf',5)
dog_1.bark()
```
## Abstracción
Denota las características esenciales de un objeto, donde se capturan sus comportamientos. Cada objeto en el sistema sirve como modelo de un "agente" abstracto que puede realizar trabajo, informar y cambiar su estado, y "comunicarse" con otros objetos en el sistema sin revelar "cómo" se implementan estas características. 

Los procesos, las funciones o los métodos pueden también ser abstraídos, y, cuando lo están, una variedad de técnicas son requeridas para ampliar una abstracción. 

El proceso de abstracción permite seleccionar las características relevantes dentro de un conjunto e identificar comportamientos comunes para definir nuevos tipos de entidades en el mundo real.

## Encapsulamiento
Significa reunir todos los elementos que pueden considerarse pertenecientes a una misma entidad, al mismo nivel de abstracción. Esto permite aumentar la cohesión (diseño estructurado) de los componentes del sistema, es decir, se puede restringir el acceso a atributos y métodos.

Existen dos formas de crear atributos privados en Python:

- **Forma 1:** Con un guion bajo delante del nombre del atributo, esto establece por convención que el atributo es privado pero no es realmente a nivel de código.

- **Forma 2:** Con doble guion bajo delante del nombre del atributo, de esta forma si son privados a nivel de código.

## Herencia
Las clases no se encuentran aisladas, sino que se relacionan entre sí, formando una jerarquía de clasificación. Los objetos heredan las propiedades y el comportamiento de todas las clases a las que pertenecen.

La herencia organiza y facilita el polimorfismo y el encapsulamiento, permitiendo a los objetos ser definidos y creados como tipos especializados de objetos preexistentes. Estos pueden compartir (y extender) su comportamiento sin tener que volver a implementarlo.

```Python
#Clase base o padre
class Quadrilateral:
    def __init__(self,sides):
        self.sides = sides
    
    def perimeter(self).
        return self.sides

#Clase heredara o hija
class square(Quadrilateral):
    def __init__(self,sides):
        super().__init__(sides)

'''super() es una función que 
permite acceder a los atributos 
y métodos de la clases base'''
```
### Herencia multiple
Una clase puede derivarse de mas una clase base, adquiriendo todos los atributos y métodos son heredados

```Python
#Clase base1
class Base_1:
    pass

#Clase base2
class Base_2:
    pass

#Clase multi heredara
class Son_1(Base_1,Base_2):
    pass

'''herencia multi nivel es heredar
de una clase ya hija de otra clase'''
#Clase que utilízala herencia multi nivel
class Son_2(Son_1):
    pass

'''pass es una operación nula,
cuando se ejecuta, nada pasa'''
```

## Polimorfismo
Comportamientos diferentes, asociados a objetos distintos, pueden compartir el mismo nombre; al llamarlos por ese nombre se utilizará el comportamiento correspondiente al objeto que se esté usando.

```Python
#Clase base
class Animal:
    def talk(self):
        pass

class Dog(Animal):
    def talk(self):
        print('guau')

class Cat(Animal):
    def talk(self):
        print('miau')

class Cow(Animal):
    def talk(self):
        print('muuu')

animals = [Dog(),Cat(),Cow()]
for animal in animals:
    animal.talk()

#output
guau
miau
muu
```