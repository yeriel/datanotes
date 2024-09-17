## ¿Que es Python?

Python es un lenguaje de programación de alto nivel interpretado, dinámico y multiplataforma, cuya filosofía hace hincapié en la legibilidad del código. Este es un lenguaje  multiparadigma, es decir, se puede escribir código en diferentes paradigmas de programación ya sea imperativo, orientado a objetos o funcional.

Python utiliza la indentación para indicar donde empieza y donde termina un bloque de código. Esto genera un código limpio y fácil de leer, ademas se pueden añadir comentarios para dejar en claro que es lo que hace el código.

## Variables 
Las variables permiten guardar valores que se pueden reutilizar en diferentes partes del código. Para crear una en Python se debe especificar un nombre y asignarle un valor.  

```python
'''
Este es un ejemplo de 
comentario largo en python
'''
def function():
    variable_a = 2 #Este es un ejemplo de como crear una variable
    return variable_a
print(function)
```

## Tipos de datos
Los objetos que contienen los datos en Python pueden ser de dos estilos mutables (son aquellos que se pueden modificar) e inmutables (Son aquellos que no se pueden modificar).

- Inmutables:  tuplas (tuples), conjuntos (set).  
- Mutables: enteros (int), decimales (float), complejos (complex), cadena texto (string/str), listas (list), diccionarios (dict).

| Tipo         | Clase   | Valor                         | Descripción                   |
|--------------|---------|-------------------------------|-------------------------------|
| Booleanos    | bool    | True o False                  |
| Entero       | int     | 100                           |
| Decimal      | float   | 100.500                       |
| Complejo     | complex | 100-10j                       |
| Cadena texto | str     | 'esto es una cadena de texto' |
| Lista        | list    | [ 1,'lista',2.3,4+2 j]        | Colección de datos mutables
| Tupla        | tuples  | ( 1,2,3,4,5 )                 | Colección de datos inmutables
| Diccionario  | dict    | { 1 : 'uno', 2 : 'dos'}       | Llave son inmutables los valores mutables
| Conjunto     | set     | {1,2,3,4}                     | Tiene solo valores únicos

## Tipos de operadores
### Aritméticos
Los operadores aritméticos son aquellos que se utilizan para realizar operaciones matemáticas sencillas.

| Operador | Función                                   | Ejemplos | Resultado |
|----------|-------------------------------------------|----------|-----------|
| “+”      | Sumar                                     | 2 + 2    | 4         |
| “-“      | Restar                                    | 3 – 2    | 1         |
| “*”      | Multiplicar                               | 2 * 2    | 4         |
| “/”      | Dividir                                   | 4 / 4    | 2         |
| “%”      | Módulo: Devolverá el resto de la división | 4 % 2    | 0         |
| “**”     | Exponente: Exponencial de un número       | 3 ** 2   | 9         |
| “//”     | División devuelve el entero de la misma   | 8 // 4   | 2         |

### Comparación
Los operadores de comparación son aquellos que se utilizan para comparar valores y nos devolverá True / False como resultado de la condición.

| Operador | Función                                                                 | Ejemplos | Resultado |
|----------|-------------------------------------------------------------------------|----------|-----------|
| “==”     | Si dos valores son exactamente iguales!                                 | 2 == 2   | True      |
|          |                                                                         | 2 == 3   | False     |
| “!=”     | Si dos valores son diferentes devuelve True!                            | 2 != 5   | True      |
|          |                                                                         | 2 != 2   | False     |
| “>”      | Si el valor de la izquierda es mayor que el de la derecha devuelve True | 4 > 2    | True      |
|          |                                                                         | 1 > 2    | False     |
| “<“      | Si el valor de la izquierda es menor que el de la derecha devuelve True | 1 < 2    | True      |

### Lógico
Se utiliza un operador lógico para tomar una decisión basada en múltiples condiciones. 

| Operador |                     Descripción                    |   Uso   |
|:--------:|:--------------------------------------------------:|:-------:|
|    and   |     Devuelve True si ambos operandos   son True    | a and b |
|    or    | Devuelve True si alguno de los   operandos es True |  a or b |
|    not   |  Devuelve True si alguno de los   operandos False  |  not a  |

## Control de flujo o Condicionales
En Python se puede definir una serie de condicionales utilizando if, elif o else.

```python
if condicion 1:
    #bloque de código A
elif condicion 2:
    #bloque de código B
else:
    #bloque de código C

'''Operador ternario -> es realizar un control 
de flujo en una sola linea de código. Un ejemplo
es la siguiente linea de código
'''
'mayor a 2' if x > 2 else 'menor a 2'
```
## Bucles o iteraciones
Los bucles permiten repetir una tarea en varias veces. Existen diferentes modificadores del flujo de un bucle estos son

- **else:** Se ejecutan un bloque de código cuando la condición ya no devuelve true. ==Solo valido para bucle while.==
- **break:** rompe la ejecución del bucle en cualquier momento
- **continue:** salta la iteración actual sin romper el bucle   

### While
Permite que se repita un bloque de código mientras la condición lógica tenga como resultado un valor verdadero (True)

```python
contador = 0 
while contador < 3:
    print(contador)
    contador +=1 #Es igual a contador = contador + 1
#output
0
1
2
```
### For
En Python, el bucle for es un bucle definido, es decir, se preestablece las condiciones de la iteración por adelantado.

- Iterable: Tipo de dato que se puede secuenciar como lo puede ser un string, lista, tupla o diccionario.
- Iterator: Objeto especifico que se obtiene a partir de un iterable

```python
frutas = ['kiwi','mango','piña']
for fruta in frutas
    print(fruta)

#output
kiwi
mango
piña
```
## Funciones
En Python la definición de funciones se realiza mediante la palabra reservada def mas un nombre de la función que sea descriptivo, seguido de paréntesis. 

```python
def sumar(num1, num2):
    return num1 + num2
print(sumar(1,2))

#output
3
```
En Python también existen la funciones lambda que es una función anónima, es decir, una función que no lleva nombre.

```python
lambda num1, num2 : num1 + num2
```
### Generadores
Un generador es un tipo de función que produce secuencias completas de resultados. En lugar de ofrecer un valor único.

```python
'''La forma mas básica de 
crear un generador'''
def generator():
    yield 'uno'

for valor in generator():
    print(valor) 

#output
uno 

'''Otra forma de crear 
un generador en una linea'''
generator = (i for i in range(3))

for valor in generator:
    print(valor) 

#output
0 
1
2
```
### Decoradores
Un decorador es un tipo de función la cual recibe como parámetro una función y a su vez retorna otra función, es decir,  a(b) -> c.

```python
def function_a(function_b):
    def function_c():
        #block code
        function_b()
    return function_c

@function_a
def function():
    print('Hello') 
```
Al decorar una función esta modifica su comportamiento sin tener que modificar su código. Es muy util si se quiere crear nuevas funcionalidades.

## Manejo de excepciones
Una excepción es un error detectado durante la ejecución. Para esto Python tiene las palabras reservadas try, except, finally.

```python
while True
    try: #Intenta ejecutar el código
        x = int(input('Ingrese un numero: '))
        break
    except ValueError:
        print('Oops hay un error')
```

El flujo para el manejo de excepciones primero se ejecuta el bloque try, si no ocurre ninguna excepción, el bloque except se salta y termina la ejecución pero si ocurre una excepción dentro del bloque try, el resto del bloque se salta y se ejecuta el excepción.  

