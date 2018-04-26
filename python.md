# Python 3 cheat sheet

## List Comprehension

```python
list = [1, 2, 3, 4, 5]

a = []
for i in list:
    if i > 3:
        a.append(i**2)
        
>>> a
[16, 25]
        
a = [i**2 for i in list if i > 3]

>>> a
[16, 25]

```

## Dict Comprehension

```python
dict = {'a': 1, 'b': 2, 'c': 3, 'd': 4}

d = {}
for k,v in dict.items():
    if v > 2:
        d[k] = v

>>> d
{'c': 3, 'd': 4}

d = {k: v for k,v in dict.items() if v > 2}

>>> d
{'c': 3, 'd': 4}

```

## Classes:

```python
class Person(object):
    def __init__(self, name, birthDate):
        self.name = name.lower().capitalize()
        self.birthDate = birthDate
        
    def jump(self):    
        return self.name + " is jumping"
```

```python
>>> patrick = Person('patrick', '1-1-1980')
>>> patrick.name
'Patrick'
>>> patrick.jump()
'Patrick is jumping'
```
