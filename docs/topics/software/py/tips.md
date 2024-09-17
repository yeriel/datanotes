# Tips

## One Liners

### intercambio de variables
```python 
'''1. swap variables'''
a = 5
b = 10
a,b = b,a 
```
### Compresion de listas
```python
'''2. list comprehension'''
# normal use
squares = []
for i in range(10):
    ifi i%2 == 0:
        squares.append(i*i)

# list comprehension use
squares = [i*i for i in range(10) if i%2 == 0]
```
### Operador ternario
```python
'''3. if else (ternary operator)'''
#normal use
if n > 2:
    var = 42
else:
    var = 99

#ternary operator use 
var = 42 if n > 2 else 99
```
### Prints en una sola linea
```python
'''4. print without new lines'''
#normal use
data = [0, 1, 2, 3, 4, 5]
for i in data:
    print(i, end=" ")

# print without new lines (GOAT)
print(*data) #output 0 1 2 3 4 5
```
### Dar vuelta una lista
```python
'''5. reversing a list'''
a = [1, 2, 3, 4, 5, 6]
a = a[::-1] #output [6, 5, 4, 3, 2, 1]
```
### Asignacion multiple
```python
'''6. multiple variable assignments'''
name, age, language = 'Python', 30, 'US'
```
### Obtener n° separados por espacio
```python
'''7. space separated numbers to integer list'''
user_input = '1 2 3 4 5'
my_list = list(map(int, user_input.split()))
#output [1, 2, 3, 4, 5]
```
### Lectura de archivo
```python
'''8. reading file into list'''
names = [line.strip() for line in open('names.txt','r')]
#output ['name1', 'name2', 'name3']
``` 

## Refactoring Tips

```python
''' 1. merge append into list declaration'''
# bad
players = []
players.append('name1') 
players.append('name2') 
players.append('name3') 

# good
players = ['name1','name2','name3']

'''2. use items() to directly unpack dictionary values'''
# bad
teams_by_color = {'blue':['name1','name2']}
for team_color in teams_by_colors:
    players = teams_by_color[team_color]
    if is_winning(team_color):
        advance_level(players)

# good
teams_by_color = {'blue':['name1','name2']}
for team_color in teams_by_colors.items():
    if is_winning(team_color):
        advance_level(players)

'''3. replace range(len()) with enumerate()'''
# bad
for i in range(len(players)):
    print(i,players[i])

# good
for i, player in enumerate(players):
    print(i,player)

'''4. simplify conditional into return statement'''
# bad
def function():
    if is_a('a'): #is_a return True if input is 'a'
        return True
    return False

# good
def function()
    return is_a('a')

'''5. replace yield inside for loop with yield from'''
# bad
def get_content(entry):
    for block in entry.get_blocks():
        yield block

# good more info in PEP380
def get_content(entry):
    yield from entry.get_blocks()
```
# Refactoring For Loops

```python 
'''1. don't use loops at all'''
# bad
numbers = [10,20,30]
result = 0
for num in numbers:
    result += num

# good
result = sum(numbers)

'''2. Use zip()'''
a = [1,2,3]
b = ['a','b','c']
# bad
for idx in range(len(a)):
    print(a[idx],b[idx])

# good
for val1, val2 in zip(a,b, strict=True):
    print(val1, val2)

'''3. Use itertools'''
# bad 
for item in [1,2,4,-1,4,1]:
    if item >= 0:
        print(item)
    else:
        break

# good
from itertools import takewhile
items = takewhile(lambda x: x >= 0, [1,2,4,-1,4,1])
for item in items:
    print(item)
```