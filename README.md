# PythonReference

## Commonly used
```python
values=('val1', 'val2', 'valn')
print "This is how to print a string %s %s %s" % values
```


## Conversions
| FROM/TO | tuple | list | set | dict |
| ---     | --- | --- | --- | --- |
| tuple   |   | list(tuple) | 4 | 5 |
| list    | list(tuple) |   | 4 | 5 |
| set     | set(t) | 3 |   | 5 |
| dict    | 2 | 3 | 4 |   |

## Iteration
### For each in list
 ```python
l=['a','b','c']
for x in l:
    print x    
```
### For 


## Files

## Execute external command

### Logging

### Directory Structure

### List sort with lambda
http://book.pythontips.com/en/testing/lambdas.html
https://wiki.python.org/moin/HowTo/Sorting

#### With sort
```python
a = [(1, 2), (4, 1), (9, 10), (13, -3)]
a.sort(key=lambda x: x[1])

```
#### With sorted()
https://wiki.python.org/moin/HowTo/Sorting

This will sort list a by the second value in the tuple
```python
from operator import itemgetter, attrgetter, methodcaller

a = [('Koy', 43),('Nathan', 11),('Carlo', 20)]
sorted(a, key=itemgetter(0))
# OUT: [('Carlo', 20), ('Koy', 43), ('Nathan', 11)]

sorted(a, key=itemgetter(1))
# OUT: [('Nathan', 11), ('Carlo', 20), ('Koy', 43)]
```

### Sort by key instead of index
```python
a = [{'name':'Zae', 'age':10}, {'name':'Koy', 'age': 43},{'name':'Nathan', 'age': 11},{'name':'Abigale', 'age':4}]

sorted(a, key=itemgetter('name'))
# OUT: [{'age': 4, 'name': 'Abigale'}, {'age': 43, 'name': 'Koy'}, {'age': 11, 'name': 'Nathan'}, {'age': 10, 'name': 'Zae'}]

```
### You have to create a class 
```python
class Student:
        def __init__(self, name, grade, age):
                self.name = name
                self.grade = grade
                self.age = age
        def __repr__(self):
                return repr((self.name, self.grade, self.age))
        def weighted_grade(self):
                return 'CBA'.index(self.grade) / float(self.age)
                
student_objects = [
        Student('john', 'A', 15),
        Student('jane', 'B', 12),
        Student('dave', 'B', 10),
        ]
        
sorted(student_objects, key=lambda student: student.age)
        
# OUT: [('dave', 'B', 10), ('jane', 'B', 12), ('john', 'A', 15)]         
```



## python symbols
https://learnpythonthehardway.org/book/ex37.html

## 
https://stackedit.io/editor
flow
st=>start: Start
e=>end
op=>operation: My Operation
cond=>condition: Yes or No?

st->op->cond
cond(yes)->e
cond(no)->op
