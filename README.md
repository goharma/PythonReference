# Commonly used
```python
values=('val1', 'val2', 'valn')
print "This is how to print a string %s %s %s" % values
```

# Data Structures
## List Comprehensions

## Python 2/3
### Check python version
```python
    try:
        assert sys.version_info >= (2,6)
    except:
        print "Python version not supported"
        sys.exit(1)
```

## Conversions
| FROM/TO | tuple                      | list        | set | dict |
| ------- | -------------------------- | ----------- | --- | --- |
| tuple   |                            | list(tuple) | 4 | 5 |
| list    | list(tuple)                |             | 4 | 5 |
| set     | set(t)                     | 3           |   | 5 |
| dict    | dict(zip((1,2,3),(a,b,c))) | 3           | 4 |   |

## Iteration
### For each in list
 ```python
l=['a','b','c']
for x in l:
    print x    
```

### List comprehension (Do stuff on a list)
http://treyhunner.com/2015/12/python-list-comprehensions-now-in-color/

```python
old_list=[]
new_list = [ "something with " + ITEM for ITEM in old_things if condition_based_on(ITEM)]
#             ^-- this is returned -^                           ^- if ITEM meets condition

```
is the same as 
```python
new_things = []
for ITEM in old_things:
    if condition_based_on(ITEM):
        new_things.append("something with " + ITEM)
```

### For 

## ConfigParser
```python
  
def _get_parser():
    # Creating parsers for commands
    # 1) Create a subparser
    # 2) Add options to that subparser
    # 3) Tell the subparser what function to execute when that command is passed in\
    # 4) Create the function


    parser = argparse.ArgumentParser()
    subparsers = parser.add_subparsers(help='sub-command help')

    #--------------------------------------------------------------------------
    #--------------------------------------------------------------------------
    # SUBPARSER TEMPLATE
    #--------------------------------------------------------------------------
    #--------------------------------------------------------------------------

    #--------------------------------------------------------------------------
    ## <command> Parser
    #--------------------------------------------------------------------------
    # 1) Create a subparser
    # parser_<command_name> = subparsers.add_parser('<command_name>', help='<Help text>')

    # 2) Add options to that subparser
    # parser_<command_name>.add_argument('--<positional arg 1>', help='Help text')
    # parser_<command_name>.add_argument('--<positional arg 2>', help='Help text')
    # ...
    # parser_<command_name>.add_argument('--<positional arg n>', help='Help text')

    # 3) Tell the subparser what function to execute when that command is passed in
    # parser_<command_name>.set_defaults(func=<function_name>)
        
        
# MAIN
parser = _get_parser()
args = parser.parse_args()

# parse the args and call whatever function was selected
args.func(args)
```

## Files

## Execute external command

```python

import subprocess

try:
    val=subprocess.check_output(["echo", "Hello World!"])
    print("Value is: %s" % val)
except subprocess.CalledProcessError:
    print("Command failed: %s", subprocess.CalledProcessError.output)
```

### Pipe
https://docs.python.org/2/library/subprocess.html#subprocess.Popen

```python
p1 = Popen(["dmesg"], stdout=PIPE)
p2 = Popen(["grep", "hda"], stdin=p1.stdout, stdout=PIPE)
p1.stdout.close()  # Allow p1 to receive a SIGPIPE if p2 exits.
output = p2.communicate()[0]
```


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
# OUT: [
#       {'age': 4, 'name': 'Abigale'}, 
#       {'age': 43, 'name': 'Koy'}, 
#       {'age': 11, 'name': 'Nathan'}, 
#       {'age': 10, 'name': 'Zae'}
#       ]

```
### Complex sort


### Sort class objects
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

# Python2/3
## 

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
