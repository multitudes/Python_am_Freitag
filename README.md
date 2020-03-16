# Python am Freitag  
(in progress)

> “Tell me and I forget. Show me and I remember. Involve me and I understand.”  Chinese proverb 

Introduction to Python. This is some material for a full week of the course.

Table of contents of the course:  

1.  [Installation](#Installation)  
2.  [Basics](#Basics):  
   [Variables](#Variables), [Strings](#Strings), [Integers](#Integers), [Floats](#Floats), [Booleans](#Booleans)
3. [Collections](#Collections)
4. [Control Flow](#Flow)
5. [Functions](#Functions)
6. [Read and write I/O](#io)
7. [Command Line Arguments](#Command)
8. [Classes](#Classes)
9. [Regular Expressions](#re)  
10. [Websockets and Web Requests](#sockets)  
11. [Algorithms](#Algorithms)  
12. [Jupyter Notebooks](#Jupyter)
12. [SQLite Module (in progress)](#sqlite)
13. [Exercises](#Exercises)  
14. [Some Humor](#Some_Humor)  
15. [A List of Python Resources](#resources)  


## Installation

Installation [python 3.8][3]:  
Check your version (this is the same in windows command line CMD):
```bash
$ python3 --version
```
If on macOS edit your zdh config file with `nano ~/.zshrc` to add an alias and change the command from python3 to python:
Add this to the very end and save, relaunch zsh
```bash
alias python=python3
```
Editors for Python: IDLE (comes with Python)Vim, eMacs, Sublime, Atom, PyCharm IDE.
Install PyCharm IDE.
Intro in the Python console, IDLE, PyCharm IDE.  

## Basics

Python is a general purpose dynamically typed, interpreted language.
Remember, in python indentation is important.

### Hello World
Make a new file called hello.py and run it in terminal and in pycharm.. and in interpreter.  
```python
print("hello, world”)
```
“Hello World” is a constant or a string literal.  
Python does not need curly braces, semicolons or to imports main etc.   
It works out of the box.   

### Comments in python

```python
'''this is a comment
more comment
'''
# this too
```

#### Slicing strings
ex `message = “monty python”` and `print(message[1:3])` etc
```python
message = “monty python”
print(message.find("monty"))
print(message.count("monty"))
print(message.replace("monty","python"))

```
 
### Formatting print()

Single quotes and double quotes both possible but for instance if we know our string contains single quotes we use double quotes on the outside.

Different ways to print on the console. We need no space after the hello if we use the comma variant.  
```python
answer = input("Name: ")
print("hello,", answer)
```

Get input from the user:
```python
name = input("Enter your name: ")
age = input("Enter your age :")
print("\nhello " + name + "!")
print("You are " + age + “.")
```
Here there is a small bug:
```python
num1 = input("Enter a number : ")
num2 = input("Enter a number : ")
result = num1 + num2
print(result)
```
Another option is formatting the output. The syntax is:
```python
# or print two variables with format. Automatically will keep the order of what to put in the brackets
print("{} {}".format(emp1.first, emp1.last))

# new since python3.6: you can add modifiers in the curly brackets using f
answer = input("Name: ")
print(f"hello, {answer.upper()}")

# this is also used
print('Hello %s!' % ('world'))
print('%s had %s pies.' % ('Alice', 42))

#also print the methods avalaible to the variable
print(dir(answer))
# this prints more but need to pass the name of the class in this case strings
print(help(str))

planet = "world"
print("hello " + planet + "!")

print("hello " + planet.upper() + "\n")
```
and:
```python
print(planet.isascii())
print(planet.islower())

a = len(planet)
print(a)

print(planet[0])

print(planet.index("w"))
print(planet.replace("world", "er"))
print('f' not in ‘foo') # False

print('foo' in ‘f') # False

print(‘hello'.find('oo')) #-1

```

Play a little:

```python
print(“????")
for i in range(4):
    print("?", end = “")
print("?" * 4)
```

Question if I print 4 blocks vertically what is the syntax to get rid of the last \n?
```python
print(“#\n” * 4)
```
Answer, use the end terminator ""

```python
print("#\n" * 4, end=“")
```
Print a cat 
```python
a = '''\    /\\
 )  ( ')
(  /  )
 \(__)|'''

print(a)
```

### Variables 
Object in Speicher mit einem Name. Container. Named place in memory where a programmer can store data and later retrieve it with the name. Can be changed. You get to choose the name!
In python muss mit Buchstabe oder unterstrich beginnen! Case sensitive. Letters, numbers and undescore.

Data types in C:
Bool, char, double, float, int, long, string

In Python
bool, float, int, str
And 
range -> sequence of numbers
list -> sequence of mutable values
tuple -> sequence of immutable value 
dict -> collection key value pairs, implemented as hash table 
set -> collection of unique value

#### Numbers 

Check the type with :
```python
num = 3
print(type(num)) #class int!
```

### Integers
We can of course do addition, substraction, multiplication, modulo.. division need `/` or `//` for the int usual behaviour.
```python
age = int(input("Age: "))
print(f"hello, you are at least {age * 365} days old\n")

# Prompt user for x
x = int(input(“x: “))
# Prompt user for y
y = int(input(“y: “))
# Perform arithmetic
print(f"x + y = {x + y}")
print(f"x - y = {x - y}")
print(f"x * y = {x * y}")
print(f"x / y = {x / y}")
print(f"x // y = {x // y}")
print(f"x mod y = {x % y}”)
a = -4
print(abs(a))
print(round(3.75))
print(round(3.75, 1))
# casting
print(int('3'))
```
With the math module
```python
from math import *
print(str(2) + " my fav number")
print(pow(2.3, 6))
print(max(4, 5))
print(min(4, 5))
print(round(5.4)) # up or down 
my_math = -5
print(sqrt(36))
print(floor(5.4))
print(ceil(5.4))
# convert into bin
print(bin(11))
# convert bin 101 in decimal 
print(int('102', 2))
```
#### Booleans
```python
num1 >= num2
num1 != num2
num1 < num2
# etc
```
Object can be equal to another and not the same object in memory
```python
a = [1,2,3]
b = [1,2,3]
print(a == b) #true
print(a is b) # false
print(id(a)) # 
print(id(b)) #
# now they are the same
a = [1,2,3]
b = a
print(a is b) #  true
print(id(a)) # id of object
print(id(b)) 
```

### Floats
Floating point imprecision
```python
x = float(input("x: "))
y = float(input("y: "))
z = x / y # try to do 1 / 10 
# not integer overflow but floating point imprecision
print(f"x / y = {z:.50f}") # prints 0.10000000000000000555111512312578270211815834045410
# this is because 1/10 in bin is 0.00011001100... etc to infinite.
# so we would get 0+0+0+0+1/16 + 1/32 + 0 + 0 + 1/256 + 1/512 ... etc (0.099609375 +...)
# print mit zero digits..
print(f"{sum2(10):.0f}")
```

## Collections
### Lists
Reference type!
List is a kind of collection.A list can contain any other python object and Uses square brackets.  
It can contain heterogeneous elements.  
Lists are mutable. Strings are immutable. Lists can be concatenated.  
Range function returns a range of numbers excluding parameter. 
Range is an iterator in python3. Need to be converted to list.  
Start with empty list.. the ‘in’ and ‘not in’ operator. There is a sort() method.  
sorted() returns a new sorted list, leaving the original list unaffected. list.sort() sorts the list in-place, mutating the list indices, and returns None (like all in-place operations).  

```python
friends = ["Kevin", "Karin", "John", 2]
print(friends[2])
print(friends[-2])
print(friends[1:])
print(friends[1:3])
friends[1] = 22
print(friends[1])
print('Karin' in friends)) # true
print(friends.find('Karin'))
for name in friends:
   print(name)
for name in enumerate(friends, start=1):
   print(name, index)
# create 
a = list()
print(list(range(6)))
print(list(range(1,6,2))

scores=[]
scores.append(72)
scores.append(73)
print(max(“hello”)
numbers = [3, 4, 5, 6]
print(min(numbers))
print(max(numbers))
print(sum(numbers))
friends.extend(numbers) # extend is appending a list! otherwise appending a list would nest it!
print(friends)
friends.append("joe")
friends.insert(2, “me")
print(friends.count(“joe”))
friends.remove("Kevin")
print(friends)
# friends.clear()

# popped will return the variable popped, which is the last in the list!
popped = friends.pop()
print(popped)
print(friends.count("joe"))
friends.remove('me')
friends.remove('John')
friends.reverse()
print(friends)
print(friends.index(22))
friends.reverse()
friends.sort() #inplace
friends.sort(reverse=True)
list(reversed(a)) # reversed(a) is a range! so need to make it a list
print(friends)
friends2 = friends.copy()
#join
a = ["a", "b", "c"]
print(“'".join(a))

# compute average
scores=[72, 73, 33]
scores.append(33)
print(f"Averages: {sum(scores) / len(scores)}")
```
#### Tuples
We cannot append or remove but we can do much of the same things as in lists  
Tuples are like lists, indexed at zero, can be iterated. Like strings are not modifiable.
Tuples can be sorted. We can sort dictionary using the items() 
```python
y = (2,4,5,66)
for i in y:
    print(i)
print((max(y)))

(x,y) = (2, "Jo")
print(y)

print(sorted(counts.items()))
```
Sort by values. Create a list of tuples key value and invert and append
```python
tmp = list()
for (key, value) in counts.items():
    tmp.append((value, key))
tmp = sorted(tmp)
print(tmp)
```
Shortest !
```python
print(sorted([ (v,k) for k,v in counts.items() ]))
```
The ten top!
```python
for value, key in tmp[:10]:
    print(key, value)
```
Tuples are immutable

```python
coordinates = (4, 5)
coordinates[0] = 11
# no changes supported in tuples they are immutable
print(coordinates)
```
<h3 id="Swap">Swapping values in Python</h3>

In Python it is very easy to swap two values like the below example with two ints:

```python
# Swaps two integers
x = 1
y = 2
print(f"x is {x}, y is {y}")
x, y = y, x
print(f"x is {x}, y is {y}”)
```

In c for comparison:

```c
int a = 1;
int b = 2;

int tmp = a;
a = b;
b = tmp;
```
### Sets
Don't care about order. Sets dont take duplicate values. Sets are optimized for membership like checking if `num in set1` or intersection of elements `set3 = set1.intersection(set2)`, or which elements are not in common with difference `set4 = set1.difference(set2)` and union of both sets `set3 = set1.union(set2)`.
Create an empty set with `emptyset = set()`



## Dictionary
Dictionary allow us to work with key value pairs. In other languages also known as hashtables
Dictionaries are not ordered! Imagine we use a look up tag! Init with dict()
Key value pairs. Single quotes are necessary in dict for the keys
A common use of dictionaries is counting how many times we see a value. Ex the frequency of words in a text.  
It is an error to reference a key which is not in the dict. integers can be keys too
We use the in operator to check wether a key is in the dict:   
```python
# empty dict
student = {}
student = {'name':'John', 'age': 25, 'courses':["math", "CompSci"]}
print(student['name']) 
# be careful accessing keys if they do not exists program will exit with error. Get name is better , with default val
print(student.get('name','not found'))
#add a key
student['phone'] = '555-5555'
student.update({...}) # takes a dict 
del student['age']
age = student.pop('age')
print(age)
```
Items in the dict are (key, values) tuples !
```python
print((counts.keys()))
print((counts.values()))
print((counts.items()))
```
We can loop through the keys(default):  
```python
for key in counts:
    print(key, counts[key])
```
This will loop through items
```python
for key, value in counts.items():
    print(key, value)
```
Creating a dict. Check the frequency of letters:
```python
counts = {}
pangram = "The quick brown fox jumps over the lazy dog"
for letter in pangram:
    if letter not in counts:
        counts[letter] = 1
    else:
        counts[letter] = counts[letter] + 1
print(counts)
# Better: Instead of checking if a key is already in the dic use the get methode with a default

pangram = "The quick brown fox jumps over the lazy dog"
for letter in pangram:
    counts[letter] = counts.get(letter, 0) + 1
print(counts)
```
Get the high count of a letter
```python

for (key, value) in counts.items():
    print(key, value)

high_letter = None
high_count = None
for letter, count in counts.items():
    if letter == " ":
        continue
    if high_count is None or count > high_count:
        high_letter = letter
        high_count = count
print("The highest letter count is :",(high_letter, high_count))
```

Simple exercise using exit():
```python
from sys import exit
people = {
    "me": "123-123456",
    "sarah": "321654987",
    "marco": "654-64567987",
    "David": "123-5558887"
}
if "David" in people:
    print(f"\nFound {people['David']}")
    exit(0)
else:
    print("\nNot Found")
    exit(1)
```


<h2 id="Flow">Control Flow</h2>

#### Condition
No switch cases in Python.
There is `and`, `not` and `or` keyword.
```python
if True:
   print('True")

language = 'python'
if language == 'python':
   print(language)
elif language == 'Java':
   print('language is Java')
```
`None` evaluate to `False` like `0` and empty sequences mapping and lists: `''`, `[]`, `{}`, `()`. All other numbers eval to `True`



Example:
```python
# Logical operators

# Prompt user for answer
c = input(“do you agree?  ")

# Check answer
if c == "Y" or c == "y":
    print("yes")
elif c == "N" or c == "n":
    print(“no")
```
Better
```python
s = input("Do you agree? \n ")

# Check answer
if s.lower() in ["y", "yes"]:
    print("\nagreed!")
elif s.lower() in ["n", "no"]:
    print(“no")
```
Comparing:
```python
# Prompt user for x
x = int(input(“x: “))
# Prompt user for y
y = int(input(“y: “))
# Compare x and y
if x < y:
    print("x is less than y")
elif x > y:
    print("x is greater than y")
else:
    print("x is equal to y")

```

Compare two strings is easy in Python:

```python
# Get two strings
s = input("s: ")
t = input("t: ")
# Compare strings for equality
if s == t:
    print("same")
else:
    print(“different”)
```

### Loops

(No do while loops in python!)

This give us opportunities for better design
```python
print("hello")
print("hello")
print(“hello")
```
Better design:
```python
for i in range(3):
    print("hello")
friends = ["joe", "tim", "luke"]
len(friends)

for friend in friends:
    print(friend)
for index in range(len(friends)):
    print(friends[index])
```
Continue and break
```python

nums = [1,2,3,4,5]

for num in nums:
   if num ==3:
      continue
   if num == 4:
      break
   print(num)   

# inner loops also possible
for num in nums:
   for letter in 'abc':
      print(num, letter

# loop for a number of times
for i in range(3, 10):
    print(i)
for i in [3,4,5,6,7,8,9]:
    print(i)
```
```python
for i in reversed(range(10)):
    print i

for n in range(6,0,-1):
    print n

while True:
    line = input("> ")
    if line[0] == "#":
        continue
    elif line == "done":
        break
    else:
        print("Line: ", line)
print("Finished!")
```


## Integer overflow!
```python
from time import sleep
# Iteratively double i
i = 1
while True:
    print(i)
    i *= 2
    sleep(1)
```

## floating point imprecision
```python
x = float(input("x: "))
y = float(input("y: "))
z = x / y
# not integer overflow but floating point imprecision
print(f"x / y = {z:.50f}")
# print mit zero digits..
print(f"{sum2(10):.0f}")
```
## Strings
```python
s = input("Input: ")
print("Output:")
for c in s:
    print(c)
```

#### Iterate on characters
```python
s = input("Input: ")
print("Output:", end="")
for i in range(len(s)):
    print(s[i], end="")
```
#### Uppercase 
```python
s = input("Input: ")
print("Output:", end="")
print(s.upper())

c = 'p'
print("The ASCII value of '" + c + "' is", ord(c))
print(chr(65))

line = "From laurent.brusa@me.com Sat Jan 5 09:15:55 2020"
words = line.split()
email = words[1]
email_pieces = email.split("@")
```

## Functions 
Functions are instructions packaged together which execute a specific task.
Use the `pass' keyword if you want to fill in the function later.
If function dont have a return value they return `None`
Allow us to reuse code and put it in a specific location without to repeat it. **#DRY**
Takes an input and produces a result. For the beginning think of a function a bit like a black box.
When we pass a variable to a function it will be only visible locally and not exist outside its local scope.

```python
def say_hi() :
    print("Hello")

print("top")
say_hi()
print("bottom")

def say_hi(name):
    print("hello" + name)

say_hi("steve")
```
Using the return statement
```python
# This will not return nothing..
def cube(num):
    num * num * num

cube(2)

#need a return statement
def cube(num):
    return num * num * num

a = cube(2)
print(a)

```
Default value
```python
def hello_func(greeting,name='you'):
   return '{}, {}'.format(greeting, name)

print(hello_func('Hi'))

```

```python
def raise_to_power(base, power):
    result = 1
    for index in range(power):
        result = result * base
    return result

print(raise_to_power(3, 4))
print(raise_to_power(3, 5))
```
Replace vowels or letters
```python
def translate(name):
    translation = ""
    for letter in name:
        if letter in "aeiouAEIOU":
            translation += "g"
        else:
            translation += letter
    return translation

print((translate("giraffe")))
print((translate(input("\n enter name: "))))
```

```python
def main():
    for i in range(3):
        hello()
def hello():
    """hello once"""
    print(“hello")
if __name__ == "__main__":
    main()
```

```python
def main():
    hello(3)
def hello(n):
    """hello some number of times"""
    for i in range(n):
        print("hello")
if __name__ == "__main__":
    main()
```
#### `*args` and `**kwargs`
Allow us to accept an arbitrary number of arguments
```python
def student_info(*args, **kwargs):
   print(args) # tuple of our parameters
   print(kwargs) # dictionary
   
student_info('math', 'art',name = 'john',age= 22)
# also
courses = ['math', 'art'] # list
info = {name = 'john', age= 22} # dict
# these will be unpacked using asterisks!
student_info(*courses, **info) # same output
```


#### lambda
Lambdas Are Single-Expression Functions. Try in the interpreter:
```python
add = lambda x, y: x + y
print(add(5, 3))

(lambda x, y: x + y)(5, 3)

```
## Get positive int

In Python the scope of a variable is the whole function!
```python
def main():
    i = get_positive_int("Positive integer: ")
    print(i)
def get_positive_int(prompt):
    """Prompt user for positive integer"""
    while True:
        n = get_int(prompt)
        if n > 0:
            break
    return n
if __name__ == "__main__":
    main()
```

## Import

Make a file called useful.py
In the file put this 
```python
print("imported module")
test = 'test string

import Random    
def roll_dice(num):
    return random.randint(1, num)
```

In a new file you call this function inserting the import on the top:
```python
import useful_tools

print(useful_tools.roll_dice(10))
```
It will print the first line of the first file! Do we want this? When we import a file it runs all the functions and instructions we have in that file.. To use the function in the first file we need to type `useful_tools.roll_dice(10)`
Also we can use `from useful_tools import roll_dice as roll, test`
and `from useful_tools import *` but frown upon, because harder to track down problems.

Check the docs for more modules!
Also to the list of directories where python looks for modules when importing: `import sys` and `print(sys.path)`
What when the file we want to import is not in the same dir? We can manually add the dir to the path: `sys.path.append('/Users/laurentb/Desktop/my_module)` better is however changing the environment variable.
Edit the `~/.bash_profile` or `~/.zshrc` for mac adding to the end `export PYTHONPATH='/Users/laurentb/Desktop/my_module`.
Now our folder is on the path! 
On Windows, start button, right click on computer, go to properties, advanced system settings and environment variable. Tap on New and enter in uppercase PYTHONPATH and the path (with backslashes)

### Standard Library
`sys.path` looks at the standard library directory. We are able to import without problems. Ex random module from the standard lib.
`import random`. For math there is the `math` module. `import datetime` and `datetime.date.today()`, `calendar`.
`os` is very useful. Current dir is `os.getcwd()`, getting the location of the file in the standard lib is `os.__file__`
We can see the whole standard library!

#### QR
```python
import qrcode
#pip install qrcode
image = qrcode.make("https://youtu.be/oHg5SJYRHA0")
image.save("qr.png", "PNG")
```

#### Explanation of __main__
It is the name of the first module run.
When we run this file directly Python sets the value of __name__ to main
if we import this file as a module in another file and run the code, it will set the name variable to the name of the module.
In file first_module.py:
```python
print("First Module name: {}".format(__name__))
# prints -> First Module name: __main__
# and this variable can be used in the second module
my_cat = "Tommy"
```
in second_module.py
```python
import first_module
# run it and it will print
# prints -> First Module name: first_module
```
To avoid exectting the Python file by import it then makes sense to execute the code only if running the file directly
ex in the second module will:
```python
import first_module

def main():
    print(first_module.my_cat) # prints Tommy

if __name__ =='__main__':
    main()
```    
Another sanity check, change the first module to:
```python
if __name__ =='__main__':
    print("run directly")
else:
    print("run from import")
```    
#### bit of functional
```python
nums = list(range(10))
def func_square(nums):
    return [num * num for num in nums]
a = func_square(nums)
print(a)

# sorting dict
a = sorted( [(b,a) for (a, b) in counts.items()] )
print(list(reversed(a))[:3])
```
## Try and except
Basic:
```python
try:
    number = int(input("enter a number "))
    print(number)

except:
    print("Invalid")
```
better:
```python
try:
    value = 10 / 0
    number = int(input("enter a number "))
    # also int in base 2! int(input("input a number : "), 2)
    print(number)

except ZeroDivisionError as err:
    print("division by zero")
    print(err)

except ValueError:
    print("invalid input”)
```


<h2 id = "io">Read and write I/O</h2>

Opening a file. The open() function returns a file handle
.read() is the whole string!

```python
import csv
file = open("notebook.csv", "a")
name = input("name ")
phone = input("phone ")
writer = csv.writer(file)
writer.writerow((name, phone))
file.close()
```
or
```python
import csv
name = input("name ")
phone = input("phone ")
with open("notebook.csv", "a") as file:
    writer = csv.writer(file)
    writer.writerow((name, phone))
```
Use the mbox file:
```python
fhand = open('mbox-short.txt')
for line in fhand:
    if line.startswith("From:"):
        print(line, end="")
# Or for the returns  
    line = line.rstrip()
```
Or better
```python
file_name = input("File: ")
try:
    fhand = open(file_name)
except:
    print("file cannot be opened")
    quit()
for line in fhand:
    if line.startswith("From:"):
        line = line.rstrip()
        print(line)
```

```python
text_file = open("text.txt", “r") # when “w” not readable! default is read, w overwrites!
print(text_file.readable())
text_file.close()

print(text_file.read())
print(text_file.readline())
```


## Classes 

Create a student class in a file Student.py
```python
class Student:
    def __init__(self, name, fach):
        self.name = name
        self.fach = fach
```
In dem anderen file:
```python
from Student import Student
from Student import Question

student1 = Student(“jim","Business")

print(student1)
print(student1.name)
print(Student)

```
## Constructor and deconstructor
Destructor is seldom used. Constructor is optional. 
```python
class Student:
    x = 0
    name = ''
    def __init__(self, nam):
          self.name = nam
        print(self.name,'constructed')
    def party(self) :
        self.x = self.x + 1
          print(self.name,'party count',self.x)
    def __del__(self):
            print(self.name, 'I am deconstructed')
```

```python
class Employee:

    # equivalent of a static variable in python but can be adjusted in instamces as well!
    raise_amount = 1.04
    # this only static because in the init!
    nums_of_empl = 0 
    
    def __init__(self, first, last, pay):
        self.first = first
        self.last = last
        self.pay = pay
        self.email = first + '.' + last + '@company.com'
        Employee.nums_of_empl += 1
        
    def fullname(self):
        return "{} {}".format(self.first, self.last)
    
    def apply_rise(self):
        self.pay = int(self.pay * self.raise_amount)
        
emp1 = Employee('Corey', 'Schafer', 50000)
emp1.age = 30
# check why self is needed in the method
print(emp1.email)
# print two variables with format
print("{} {}".format(emp1.first, emp1.last))
# both are the same
print(emp1.fullname())
print(Employee.fullname(emp1))
# print content of an instance and a class. see the raise_amount is only in the class
print(emp1.__dict__)
print(Employee.raise_amount)

# this is different in Python!
# I change the instance raise_amount and it changes it only in the instance.
# so the raise_amount is both static and attribute
emp1.raise_amount = 2
print(emp1.raise_amount)

#also using the raise_amount in the class as self.raise_amount) or Employee.raise_amount makes a world of difference

#class methods as alternate constructors. ex I want to construct an employee from string - add this to class
    @classmethod # this is called a decorator
    def from_string(cls, emp_string):
        first, last, pay = emp_string.split('-')
        return cls(first, last, pay)

emp_str_1 = "john-doe-50000"
new_emp1 = Employee.from_string(emp_str_1)  #this uses a class method returning an instance!
#static methods do not take cls or self as param add to class with decorator staticmethod and import datetime 
@staticmethod
    def is_workday(day):
        if day.weekday() == 5 or day.weekday == 6:
            return False
        return True

my_date = datetime.date(2016,7,10)
print(Employee.is_workday(my_date))

# super useful help function to see inheritance from classes
print(help(Dev))
 
# Python has multiple inheritance! lets make a subclass and use super()__init__ when single inheritance or Employee.__init__(self,... )if multiple inheritance

class Dev(Employee):
    def __init__(self, first, last, pay, prog_lang):
        super().__init__(first,last,pay)
        self.prog_lang = prog_lang

# and again a manager will manage a list of Employees. Do not init with a mutable empty list! Use None
class Manager(Employee):
    def __init__(self, first, last, pay, employees=None):
        super().__init__(first,last,pay)
        if employees == None:
            self.employees = []
        else:
            self.employees = employees
    def add_emp(self, emp):
        if emp not in self.employees:
            self.employees.append(emp)
    def remove_emp(self, emp):
        if emp in self.employees:
            self.employees.remove(emp)
    def print_emps(self):
        for emp in self.employees:
            print("---> ", emp.fullname())
            
emp1 = Employee('Corey', 'Schafer', 50000)
mng2 = Manager('Ann', 'Smith', 90000,[emp1])
mng2.print_emps()

#is instance and is subclass
print(isinstance(mng1, Manager))
print(issubclass(Employee, Manager)) #false
print(issubclass(Manager, Employee)) #true


```
#### Magic/Dunder Methods
```python
print(emp1) # prints <__main__.Employee object at 0x10c834850>

#but __repr__ is used in the class to represent our object for debugging etc. Put this in the Employee class
    def __repr__(self):
        return "Employee('{}', '{}', '{}')".format(self.first, self.last,self.pay)
    def __str__(self):
        return '{} - {}'.format(self.fullname(), self.email)
# and now run print(emp1) again..
#also
print(repr(emp1))
print(str(emp1))

#other magic or dunder methods is the addition, which in the background is
print(int.__add__(1,2))
print(str.__add__("1","2"))
# add this in your class
    def __add__(self, other):
        return self.pay + other.pay
# then you can add two classes.. this just for the sake of explaining
print(emp1 + emp2)
```
#### Property Decorators - Getters, Setters, and Deleters
The problem above is that the email is created initializing the instance with the name but then if the name changes the email doesnt change . for this we use property decorators. remove the email from the class and add it as method with the decorator property. This will help to keep using the existing code. Without decorator I would need to use the email() method. With @property I can just do `emp1.email` 
```python
    @property
    def email(self):
        return "{}.{}@company.com".format(self.first, self.last)
```
If I want to set the first and last name in one go giving a string like 'Richard Smith' I use a setter like this. Different syntax using `@fullname.setter`:
```python
    @property
    def fullname(self):
        return "{} {}".format(self.first, self.last)

    @fullname.setter
    def fullname(self,name):
        first, last = name.split(' ')
        self.first = first
        self.last = last
# ex        
emp1.fullname = 'Richard Smith'        
```
There is a deleter too. So this will look like 


```python
    @fullname.deleter
    def fullname(self):
        print("delete!")
        self.first = None
        self.last = None

del emp1.fullname        
```

#### Exercise : create a Frage class… for Quiz

ex:
```python
question_prompts = ["What color are oranges? \n(a) orange \n(b) green\n”, "what color are bananas: \n(a) red\n(b) yellow\n"]
questions = [Question(question_prompts[0],"a"),
             Question(question_prompts[1], "b")]
def run_test(questions):
    score = 0
    for question in questions:
        answer = input(question.prompt)
        if answer == question.answer:
            score += 1
    print("you got a score of : " + str(score) + "/" + str(len(questions)) + " correct")

run_test(questions)
```
## Inheritance
One file:
```python
class Chef:

def make_chicken(self):
    print("I make chicken\n")

def make_salad(self):
    print("i can make salads! \n")

def make_special(self):
    print("here come a rib!")
```
Another file:
```python
from Chef import Chef

class ChineseChef(Chef):

    def make_fried_rice(self):
        print("I make fried rice!")

    def make_special(self):
        print("here comes a duck!”)
```
Another file:
```python
from Chef import Chef
from ChineseChef import ChineseChef

mychef = Chef()
mychef.make_chicken()
mychef.make_special()

myChineseChef = ChineseChef()
myChineseChef.make_fried_rice()
myChineseChef.make_special()
myChineseChef.make_chicken()
```

<h2 id = "Command">Command Line Arguments</h2>


Offset by one in python
```python
from sys import argv
for i in range(len(argv)):
print(argv[i])
if len(argv) == 2:
    print(f"hello, {argv[1]}")
else:
    print("hello, world")
```
#### shebang
In Unix systems the shebang is `#!/usr/bin/env python3`, on windows maybe with `/usr/bin/env` or `#! python3` but did not try yet!
(unix) Need to make the file executable in terminal with :
```bash
chmod +x hello.py
```

```python
#!/usr/bin/env python3
import sys
def main():
    if len(sys.argv) >= 2:
        name = sys.argv[1]
    else:
        name = 'world'
    print('hello',name)

if __name__ == '__main__':
    main()
```    
Exit with value:
```python
from sys import argv, exit
if len(argv) < 2:
    print("missing command line argument \n")
    exit(1)
exit(0)
```
Array property ‘in’
```python
from sys import exit
names = ['me', 'sarah', 'marco', 'steve']
name = input("name: ")
if name in names:
    print("\nFound")
    exit(0)
else:
    print("\nNot Found")
    exit(1)
```

<h2 id = "re">Regular expression</h2>

(See the quick guide in the folder)
Need to import re, re.search() to match re.findall() to extract
Start with :
```python
# Check answer
s = input("Do you agree? \n")
if s.lower() in ["y", "yes"]:
    print("\nagreed!")
elif s.lower() in ["n", "no"]:
    print("no")
```
And
```python
import re
s = input("Do you agree? \n")
# Check answer
if re.search("yes", s):
    print("\nyes agreed!")
elif re.search("no", s):
    print("not agreed")
else:
    print("I do not know”)
```
Or change to 
```python
if re.search("yes|y", s):

if re.search("y(es)?", s):

if re.search("y(es)?", s, re.IGNORECASE):

if re.search("^y(es)?$", s, re.IGNORECASE):
```
With emails. In mbox file
```python
import re
fhand = open('mbox-short.txt')
for line in fhand:
    if re.search("^From:", line):
        print(line, end="")
# Or for the returns
    line = line.rstrip()
for line in fhand:
if re.search("^X.*:", line):
    print(line, end="")
```
```python
x = "My 2 favorite numbers are 42 and 19"
y = re.findall("[0-9]+", x)
print(y)
```
Greedy matching with * +
```python
x = "From: using the colon again here : and see"
y = re.findall("^F.+:", x)
print(y)
```
\S is one non whitespace character
```python
import re
fhand = open('mbox-short.txt')
text = fhand.read()
y = re.findall("From: (\S+@\S+)", text)
print(y)
```
\$ is one real dollar sign
```python
x = "a real $10 bill"
y = re.findall("\$[0-9]+", x)
print(y)
```
Or this syntax. The first returns all vowel in an array, the second all consonants
```python
vowelRegex = re.compile(r'[aeiouAEIOU]')
vowelRegex.findall('Alice was beginning to get very tired of sitting by her sister
on the bank, and of having nothing to do')
consonantRegex = re.compile(r'[^aeiouAEIOU]')
consonantRegex.findall('Alice was beginning to get very tired of sitting by her sister
on the bank, and of having nothing to do')

atRegex = re.compile(r'.at')
atRegex.findall('The cat in the hat sat on the flat mat.')

nameRegex = re.compile(r'First Name: (.*) Last Name: (.*)') 
mo = nameRegex.search('First Name: Laurent Last Name: Brusa')
print(mo.group(1),mo.group(2))
```
<h2 id="sockets">Websockets and Web Requests</h2>

### Websockets

End systems are hosts like server and client host. Network-core devices are routers etc
two predominant architectural paradigms used in modern network applications: the client-server architecture or the peer-to-peer (P2P) architecture. 
In a client-server architecture, there is an always-on host, called the server, which services requests from many other hosts, called clients. 
In the jargon of operating systems, it is not actually programs but processes that communicate. A process can be thought of as a program that is running within an end system. 

Network socket also internet socket . Endpoint of bidirectional communication flow across a protocol based network
One endpoint of two way communication link between two programs running on the network. 
Combination of an IP and port number. Created first without ip, only port 
Commands are socket, bind, send , listen, recv and close

Tcp well known ports = 23 was telnet , 22 ssh, http 80, https 443, smtp 25, imap 143/220/993, pop 109/110, dns 53, ftp 21
Python has built in support for tcp sockets
Standardisierte Ports (0–1023) Auf Unix-artigen Betriebssystemen darf nur das Root-Konto Dienste betreiben, die auf Ports unter 1024 liegen. Registrierte Ports: 1024–49151
Dynamische Port-Adressen von 49152 - 65535 . dynamische Ports, die von Anwendungen lokal und/ oder dynamisch genutzt werden können.

Client:
```python
from socket import *
# the IP address of the server
serverName = '0.0.0.0'
# the server port
serverPort = 12000
# I create a socket to communicate. I will get a port from the available ones
clientSocket = socket(AF_INET, SOCK_DGRAM)
# get the message from user
message = input('Input lowercase sentence:')
# encode and send to server
clientSocket.sendto(message.encode(), (serverName, serverPort))
# this is what I get back from server. the number is the buffer size
modifiedMessage, serverAddress = clientSocket.recvfrom(2048)
print("This is the message I received from server: \n", modifiedMessage.decode())
clientSocket.close()
```
Server side
```python
from socket import *
# this file will be on my server
#create a server in python-go to directory and enter in terminal
# python3 -m http.server 12000
serverPort = 12000
# create socket
serverSocket = socket(AF_INET, SOCK_DGRAM)
# need to bind the socket to the port
serverSocket.bind(('', serverPort))
# server is waiting
print('The server is ready to receive')
while True:
    # this is a tuple I get with message and client address
    message, clientAddress = serverSocket.recvfrom(2048)
    # if I didnt get anything keep on listening
    if len(message) != 0:
        # if I get a message decode it and change it for ex make it upper
        modifiedMessage = message.decode().upper()
        print("received a message from server address: ", clientAddress,
              "\n and I changed it to upper case! : \n",
              modifiedMessage)
        # send
        serverSocket.sendto(modifiedMessage.encode(), clientAddress)
```
With urllib
```python
import urllib.request, urllib.parse, urllib.error
fhand = urllib.request.urlopen('http://data.pr4e.org/romeo.txt')
counts = dict()
for line in fhand:
    words = line.decode().split()
    print(words)
    for word in words:
        print(word)
        counts[word] = counts.get(word, 0) + 1
print(counts)
```
With images, ex start the local http server again
```python
import urllib.request, urllib.parse, urllib.error

img = urllib.request.urlopen('http://localhost:12000/image.jpeg').read()
fhand = open('cover3.jpg','wb')
fhand.write(img)
fhand.close()

img = urllib.request.urlopen('http://data.pr4e.org/cover3.jpg')
fhand = open('cover3.jpg', 'wb')
size = 0
while True:
    info = img.read(100000)
    if len(info) < 1: break
    size = size + len(info)
    fhand.write(info)

print(size, 'characters copied.')
fhand.close()
```


open the terminal below and enter `python3 -m http.server 81`
```python
fhand = urllib.request.urlopen('http://0.0.0.0:81/pangram.txt')
for line in fhand:
    print(line.decode().strip())
```

## Web scraping: Beautiful soup
```python
import urllib.request, urllib.parse, urllib.error
from bs4 import BeautifulSoup
url = input("enter: ")
html = urllib.request.urlopen(url).read()
soup = BeautifulSoup(html, 'html.parser')
tags = soup('a')
for tag in tags:
    print(tag.get('href', None))
```
If error due to certificates
```python
import ssl

ctx = ssl.create_default_context()
ctx.check_hostname = False
ctx.verify_mode = ssl.CERT_NONE

url = input("enter: ")
html = urllib.request.urlopen(url, context=ctx).read()
soup = BeautifulSoup(html, 'html.parser')

tags = soup('a')
for tag in tags:
    print(tag.get('href', None))
```
## Serialise and deserialise with JSON and XML
In progress

## Words in dictionary
```python
words = set()

def check(word):
    """Return true if word is in dictionary else false"""
    return word.lower() in words

def load(dictionary):
    """Load dictionary into memory, returning true if successful else false"""
    file = open(dictionary, "r")
    for line in file:
        words.add(line.rstrip("\n"))
    file.close()
    return True

def size():
    """Returns number of words in dictionary if loaded else 0 if not yet loaded"""
    return len(words)

def unload():
    """Unloads dictionary from memory, returning true if successful else false"""
    return True
```
## Pillow
(Need the Pillow module that can be eventually troublesome to install on some systems)
This is the blur effect
```
from PIL import Image, ImageFilter

before = Image.open("Mushroom.png")
after = before.filter(ImageFilter.BLUR)
after.save("out.png")
```

## Algorithms

The big O. To compare algorithms, we ask, which one is better than other?  
Considering speed and memory use.  
For loops are slow!  
We compare how quickly the runtime grows not the actual time.  
In the first function it grows proportionally to n + 1. For big numbers the “+1” is irrelevant so we just say O(n).  
We speak of asymptotic analysis. In math this is describing limiting behaviour of a function.

#### Euler problem 1
If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.  
Find the sum of all the multiples of 3 or 5 below 1000.  (233168)
Two ways. One is O(n), the other O(1)!
```python
def euler1():
    number = 0
    for i in range(1000):
        if i % 5 == 0 or i % 3 == 0:
            total += i
        continue
    return number

def euler2():
    number = 0
    a = set(range(3,1000,3))
    b = set(range(5,1000,5))
    number_set = a.union(b)
    print(number_set)
    number = sum(number_set)
    return number

```

#### sum all numbers in a range
```python
def sum1(n):
    final_sum = 0
    for x in range(n + 1):
        final_sum += x
    return final_sum

print(sum1(10))

def sum2(n):
    return n * (n + 1) / 2

print(f"{sum2(10):.0f}")
```
## Bubble
Python program for implementation of Bubble Sort
```python
def bubbleSort(arr):
    n = len(arr)
    # Traverse through all array elements
    for i in range(n):
        # Last i elements are already in place
        for j in range(n - i - 1):
            # traverse the array from 0 to n-i-1
            # Swap if the element found is greater
            # than the next element
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
# Driver code to test above
arr = [64, 34, 25, 12, 22, 11, 90]
bubbleSort(arr)
print("Sorted array is:", arr)
```

Also check:

https://projekteuler.de

https://projecteuler.net/problem=1

<h2 id = 'jupyter'>Jupyter Notebooks</h2>

This needs to be installed via command line in terminal (do not type the '$' which is your prompt). Ensure you are in the correct folder in your Python environment in PyCharm, if not navigate to it, then ensure that you have the latest pip with:

```bash
$ pip3 install --upgrade pip
```
Then install the Jupyter Notebook using:
```bash
$ pip3 install jupyter
```
then still in the same folder you start in terminal with:
```bash
$ jupyter notebook
```
Look for interesting notebook here:
[https://github.com/jupyter/jupyter/wiki/A-gallery-of-interesting-Jupyter-Notebooks](https://github.com/jupyter/jupyter/wiki/A-gallery-of-interesting-Jupyter-Notebooks)
and here for ex:
[https://nbviewer.jupyter.org/github/ipython/ipython/blob/master/examples/IPython%20Kernel/Index.ipynb](https://nbviewer.jupyter.org/github/ipython/ipython/blob/master/examples/IPython%20Kernel/Index.ipynb)

Dowload from the web and move to current folder(mac)
```bash
$ mv ~/Downloads/filename ./
```
List the Magic with `%lsmagic` in the notebook

## SQLite Module (in progress)

## Exercises

Look at the CS50 problems like: 
mario/ cash / credit cards / cesar / crack / vigenere / bleep

```
#Mario
n = 8
a: int = n
b: int = 0
for i in range(n):
    a = a - 1
    b = b + 1
    print("." * a, end="")
    print("x" * b, end="\n")
```

Both sides
```
n = 8
a: int = n
b: int = 0
for i in range(n):
    a = a - 1
    b = b + 1
    print("." * a, end="")
    print("x" * b, end=" ")
    print("x" * b, end="")
    print("." * a, end="\n")
```
#### Print out a block
```python
for i in range(4):
    # Print out this many columns
    for j in range(4):
        print("#", end="")
    print()
```

* FizzBuzz
* Fibonacci

```python
a, b = 0, 1

for i in range(0, 10):
    print(a)
    a,b = b, a+b

```
#### The Collatz Sequence
Write a function named collatz() that has one parameter named number. If number is even, then collatz() should print number // 2 and return this value. If number is odd, then collatz() should print and return 3 * number + 1.
Then write a program that lets the user type in an integer and that keeps calling collatz() on that number until the function returns the value 1.

#### Reverse Cipher
Ich habe diese message bekommen. Ich glaube es ist encrypted.
“dlrow olleh”. Schreib ein Programm um diese art von Nachrichten zu entziffern

```python
message = 'dlrow olleh'
translated = ''
i = len(message) - 1
while i >= 0:
    translated = translated + message[i]
    i = i - 1
print(translated)
```

A Three Questions Quiz game. It can be done in many different ways, 
* with if statements. 
* With reading from file
* With lists / dicts
* With oop

#### The Captcha:
You're standing in a room with "digitisation quarantine" written in LEDs along one wall. The only door is locked, but it includes a small interface. 

"Restricted Area - Strictly No Digitised Users Allowed."

It goes on to explain that you may only leave by solving a captcha to prove you're not a human. Apparently, you only get one millisecond to solve the captcha: too fast for a normal human, but it feels like hours to you.
The captcha requires you to review a sequence of digits (your puzzle input) and find the sum of all digits that match the next digit in the list. The list is circular, so the digit after the last digit is the first digit in the list.

For example:
1122 produces a sum of 3 (1 + 2) because the first digit (1) matches the second digit and the third digit (2) matches the fourth digit.
1111 produces 4 because each digit (all 1) matches the next.
1234 produces 0 because no digit matches the next.
91212129 produces 9 because the only digit that matches the next one is the last digit, 9.

What is the solution to your captcha?

https://adventofcode.com/2017/day/1

```python
# map is functional programming. can be done with a loop of course but much longer code. Why a tuple? they are immutable and I do not need to mutate the input therefore I use tuple, it is also an added security. *args and **kwargs are magic variables.
problem_input = '91212129'
digits = tuple(map(int, problem_input))
print(digits)
N = len(digits)
a = sum(digits[i]
        for i in range(N)
        if digits[i] == digits[i - 1])
print('solution is : ',a)

```

<h2 id="Some_Humor">Some Humor</h2>

https://www.xkcd.com/323/

If Python is executable pseudocode then Perl is executable line noise..
https://www.youtube.com/watch?v=zJOS0sV2a24

#### [Antigravity][1]

```python
import antigravity
def main():
    antigravity.fly()
if __name__=='__main__':
    main()
```

<h2 id = "resources">A List of Python Resources</h2>

[FastAI forums: Recommended Python learning resources][2]

* Beginners to programming  
Whirlwind Tour of Python: Nice only book that covers all the essential Python basics without overwhelming the Python novice.  
Learn Python the Hard Way: widely used book for learning Python as a first programming language
Automate the boring stuff with Python by Al Sweigart: Contains a lot of scripts to make your boring task easier.  
Python tutorials by Sentdex: This website contains everything related to python from beginner to advance level
Python OOP’s tutorial by Corey Schafer: OOP concepts in python, which are extensively used in pytorch.  
Real Python - A curated list of (long) blog posts on various aspects of Python programming from language fundamentals to advanced concepts, with applications along the way.  
Udemy complete python bootcamp: Go from zero to hero in Python 3: (paid usually available for around $19) video and notebook based course that starts from the basics of Python and builds a few small milestone projects along the way.  
Learn to Program with Python: (video course) Full multipart introduction to programming with python by Derek Banas (free).  
Introducing Python - Excellent book with lots of examples, also introducing the python ecosystem and useful packages.  
Solo Learn: This app is good for beginners and gives you the game like feeling.  
Code academy: Good for beginners as it contains exercise also which will help you to learn quickly  
Python - The No Theory Guide: Collection of Jupyter Notebooks that help you learn Python with hands-on Programming.  
Introduction to Computer Science and Programming Using Python: This is a really good course, and recommended by a good number of folks from the Reddit Python community  
* Intermediate programmers
The Hitchhiker’s Guide to Python: a book on Python from Kenneth Reitz, the author of requests library. A comprehensive introduction into Python’s eco-system and best practices.  
Peter Norvig’s Pytudes: a github repo that contains well-made jupyter notebooks, ranging in topics from Gesture Typing to A Concrete Introduction to Probability (using Python). These notebooks make for some great reads and the coding style is a good resource to learn from, especially in ways of breaking down problems in clear, readable code.  
Design of Computer Programs also by Peter Norvig on Udacity is a great programming course in general, and has good introductions to comprehensions and generators.  
Fluent Python: introduces the internals of python, helps you write more pythonic code.  
Derek Banas - Python in one video : Ideal for people that have experience in some other programming language and want a quick tour of python.  
Trey Hunner: Trey has done a lot of webcasts as well as written a lot of good article focusing on intermediate python developer.  
Python tricks by Dan bader: This book contains a lot of tricks which will make you a great Pythonista, you can also follow dan’s personal website https://dbader.org/  to learn more about the python tips and tricks.  
Google’s Python Class :Google’s Python Class is a short but great introduction to python for people who already know programming but are new to python. It is available both as video lectures and articles.  
* Advanced programmers (but maybe new to python)
Learn x in y minutes : quick overview of main Python 3 features entirely using code examples.  
David Beazley’s courses, tutorials, and books: generators, yields, descriptors, and other advanced topics  
Raymond Hettinger: If you want to master python skills then Raymond is the man, he has been a python core developer for many years and tend to give an advance talk.  
* Python numeric programming (for people that know python already)
Stanford numpy tutorial: great little intro to key python libs and concepts for numeric programming  
Python Data Science Handbook (by Jake VanderPlas) - An introduction to the major scientific Python/“PyData” packages and best practices. (Being two years old it may be slightly dated (only slightly) at a few places in terms of the API used, but it’s still a great intro and reference.) [The author has generously made available the entire book as freely available notebooks; however the book can also be purchased 16 in print and electronic formats.]  
Python for data science by wes mckinney(author of pandas): The author of pandas himself starts from basics and goes to advance features of pandas. In short great material to start learning pandas.  
* Python challenges  
https://codechalleng.es/challenges/  - It’s good if you are just starting with python  
CheckIO  - Go on an (game) adventure by solving programming challenges with Python.  
* Python podcast.  
https://talkpython.fm/  - you will fall in love with python after watching this podcast. 
https://pythonbytes.fm/  - This podcast will keep you updated about the python community and new.  
* Python Newsletters  
If you want to keep updated with the python articles, videos and more then subscribe to these channels  
https://www.pythonweekly.com/
https://importpython.com/newsletter/
https://pycoders.com/ 

Gravitational waves notebook!
https://github.com/gw-odw/odw-2019
And curl! For windows! (check Cygwin
https://curl.haxx.se/download.html

[https://www.fast.ai/2019/12/02/nbdev/](https://www.fast.ai/2019/12/02/nbdev/)


## Environments 
They are used default is PyCharm but if you need to activate them in bash:
ps do not put any of your files in venv folder. venv should not be on version control
```bash
# create project_env
python3 -m venv project_env
# activate
source project_env/bin/activate
# if you check you will see the env created
which python3
# check your modules
pip list
# create a requirements file
pip3 freeze > requirements.txt
cat requirements.txt
deactivate
# remove
rm -rf project_env
# or commonly create my project directory
mkdir myproject
python3 -m venv myproject/venv

# using a requirements.txt
pip3 install -r requirements.txt

# using a global venv
python3 -m venv venv --system-site-packages

pip3 list --local
``` 

## matplotlib

```bash
pip3 install matplotlib
```
In PyCharm:
```python
from matplotlib import pyplot as plt

dev_x = [25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35]
dev_y = [38496, 42000, 46752, 49320, 53200,
         56000, 62316, 64928, 67317, 68748, 73752]

plt.plot(dev_x,dev_y, label = 'salaries/age')
plt.title("title")
plt.legend(loc=0)
plt.show()
```
adding two graphs at once. with markers and colors(which can be hex)
```python
plt.plot(dev_x,dev_y, color='k',linestyle='--',marker=".", label = 'salaries/age')
plt.plot(dev_x,py_dev_y,color='#5a7d9a',marker="o",linewidth=3, label = 'Python salaries/age')
plt.plot(dev_x,js_dev_y,color='#444444',marker="o",linewidth=3, label = 'Python salaries/age')
# some customizations 
plt.tight_layout()
plt.grid(True)`
```
styles:
```python
# print(plt.style.available)
plt.style.use('ggplot')
```
Try the 'fivethirtyeight', 'seaborn' and 'ggplot' 

and for the xkcd feel add this instead of using a style:
'''python
plt.xkcd()
'''

## Jupyter Notebooks

To run code interactively within a webbrowser alongside visualisation and a markdown text. Based on iPython which is now rolled in the Jupyter Project. Lots of scientific institutions are using the notebooks in order to explain how they got their results
To install from their [page][4], they suggest to install Anaconda. Anaconda is a huge package and comes bundled with Jupyter.
Use the prompt to display results without using print() all the time. 
Put text in markdown cells, and code in code cells.
Using an `!` I can run the bash commands inside the notebook like:
`!pip list`
Also come with a bunch of built in commands called magic.
They beginn either with a `%` (which means the command line argument will all come from the same line) called 
*line magics* and `%%` (which means the entire cell will be executed as a command) called *cell magic*.
ex list all the magic commands split inline magic anc cell magic with:
`%lsmagic'
This will print our working directory:
`%pwd'
This works like in terminal!
`%ls -la`
Some of the most common is 
`%matplotlib inline` allows the plots to be displayed in the notebook.
For example:
```python
%matplotlib inline
import matplotlib.pyplot as plt
import numpy as np
N = 50
x = np.random.rand(N)
y = np.random.rand(N)
colors = np.random.rand(N)

area = np.pi * (20 * np.random.rand(N)) **2
plt.scatter(x, y, s=area, c = colors, alpha=0.5)
plt.show()
```
`%%HTML` is a cell magic command which allows the whole cell to be treated as HTML code. There is the `%%javascript` one and also `%%timeit` to time the code in the cell.

Panda and numpy are uesd very often in the notebooks for data science.

You can export the notebook as python file or html. The html version is not editable anymore but I can add it in my blog etc.
To share I just give the `ipynb` file which is a json format file with the contents formatted in a dictionary. Multiple kernel can be used for different versions of Python.

Here youwill find an extensive [collection of notebooks][5]

## Django
 
in terminal. Activate a new env and install Django 
```bash
$ pip install django 
$ python -m django --version 

# for a list of all subcommands
$ django-admin

# startproject will create a new project- I named mine my_django
# this creates a folder with manage.py, settings.py, urls.py files
$ django-admin startproject my_django

# run server
$ python manage.py runserver 

# it will give you a localhost address
# try http://127.0.0.1:8000/admin
```
A single project can contain multiple apps.
Create a new app with the command startapp and name

```bash
$ python manage.py startapp blog
```

edit the views file inside the folder blog

```python
# add
from django.http import HttpResponse

# Create your views here.

def home(request):
    return HttpResponse('<h1>Blog Home</h1>')
```
create a new file in the app directory and name it urls.py

```python
from django.urls import path
from . import views

urlpatterns = [
    path('/', views.home, name='blog-home'),
] 

```
Next create templetas to avoid repeating the html in the views!
Create a new 'templates' folder. By convention needs to have a dir with the same name as the app. in the blog dir then create the html template files for blog and about. 
Insert this info in the apps.py file in the app.

```python
from django.apps import AppConfig


class BlogConfig(AppConfig):
    name = 'blog'
```
open the settings.py file in the project and add the BlogConfig class in it there

```python
# Application definition

INSTALLED_APPS = [
    'blog.apps.BlogConfig',
```

make a template

get bootstraps for instance for a quick demo
https://getbootstrap.com/docs/4.3/getting-started/introduction/#starter-template

The CSS goes into a newly created static folder inside the blogapp. blog -> static -> blog -> main.css 
```python
{% load static %}

# and in the template
    <link rel="stylesheet" type="text/css" href="{% static 'blog/main.css' %}" /> 

# and you do not hardcode the links but use the urls file we had: "href="{% url 'blog-home' %}" 
# and this is encoded in urls.py in the project
          <a class="nav-item nav-link" href="{% url 'blog-home' %}">Home</a>
          <a class="nav-item nav-link" href="{% url 'blog-about' %}">About</a>
        </div>
        <!-- Navbar Right Side -->
        <div class="navbar-nav">
          <a class="nav-item nav-link" href="#">Login</a>
          <a class="nav-item nav-link" href="#">Register</a>
```

#### admin login

Get the admin login working!

```bash
$ python manage.py createsuperuser
```

But for that to work you need a database.
First you need to 

```bash 
$ python manage.py makemigrations
$ python manage.py migrate 
$ python manage.py createsuperuser
# prompt will ask for username and password!

```

Now you can login. The good thing about Django is that it comes with a really awesome admin site by default.
Django has a built in ORM Object Relational Mapper. This allows us to later change database engines without affecting our code base. You could use a sqlite db for testing and a postgres for production.
We can represent our db structure as classes and those classes as models. So lets go to the models.py. Django has a built in user model already!
We start making a POST model inheriting from the model class

```python 
from django.db import models
from django.utils import timezone
from django.contrib.auth.models import User


# Create your models here.
class Post(models.Model):
    title = models.CharField(max_length=100)
    content = models.TextField()
    date_posted = models.DateTimeField(default=timezone.now)
    author = models.ForeignKey(User, on_delete=models.CASCADE)

# this is dunder (__) / magic method to specify how the class will be descripted when printed   
    def __str__(self):
        return self.title
```
To apply those changes we need to use the ` 
command makemigrations`
```bash 
$ python manage.py makemigrations
# then we see a file in our migration folder starting like 0001_initial.py
# To see the sql being generated we do:
$ python manage.py sqlmigrate blog 0001
# then we apply what we just prepared with
$ python manage.py migrate

```
migrations allow us to make changes to our database even after it has been created. Super useful

With the shell command we can interactively operate on create the tables( classes and models)

```bash 
$ python manage.py shell

# this is our shell!
>>> from blog.models import Post
>>> from django.contrib.auth.models import User
>>> User.objects.all()
<QuerySet [<User: laurent>, <User: test>, <User: CoreyMS>]>
>>> User.objects.first()
<User: laurent>
>>> User.objects.filter(username="laurent")
<QuerySet [<User: laurent>]>
>>> User.objects.filter(username="laurent").first()
<User: laurent>
>>> user = User.objects.filter(username="laurent").first()
>>> user.id
1
>>> user.pk
1
>>> user = User.objects.get(id=1)
>>> user
<User: laurent>

# lets create posts. At the moment it is empty
>>> Post.objects.all()
# date shd be automatic
>>> post_1 = Post(title = 'Blog 1', content = 'First Post Content!', author=user)
>>> post_1.save()
>>> Post.objects.all()
<QuerySet [<Post: Blog 1>]>
>>> user = User.objects.filter(username="laurent").first()
>>> post_2 = Post(title = 'Blog 2', content = 'second  Post Content!', author=user)
>>> post_3 = Post(title = 'Blog 3', content = 'third  Post Content!', author_id=user.id)
>>> post_2.save()
>>> post_3.save()
>>> Post.objects.all()
<QuerySet [<Post: blog1>, <Post: Blog 1>, <Post: Blog 2>, <Post: Blog 3>]>
>>> post = Post.objects.first()
>>> post.content
'first'
>>> post.date_posted
datetime.datetime(2020, 3, 13, 15, 47, 12, 304878, tzinfo=<UTC>)
>>> post.author_id
1
>>> post.author
<User: laurent>
>>> post.author.email
'laurentbrusa@me.com'

# look for all post of an user
>>> user.post_set
<django.db.models.fields.related_descriptors.create_reverse_many_to_one_manager.<locals>.RelatedManager object at 0x10e633fa0>
>>> user.post_set.all()
<QuerySet [<Post: blog1>, <Post: Blog 1>, <Post: Blog 2>, <Post: Blog 3>]>
# use post_set to create post. user is implicit
>>> user.post_set.create(title='Blog 4', content='4th post content!')
<Post: Blog 4>
>>> exit()

```
Now we have dummy data in our database. Our views.py will be now 
```
from django.shortcuts import render
from .models import Post

# Create your views here.


def home(request):
    context = {
        'posts': Post.objects.all()
    }
    return render(request, 'blog/home.html', context)

def about(request):
    return render(request, 'blog/about.html', {'title': 'About'})
```

Change the format of dates. Within out template tags there are various way to change the formatting of a date field.
ex. `{{ post.date_posted|date:"F d, Y" }}`
[https://docs.djangoproject.com...builtins/#date][6]

To see the posts in the admin page on the website I will need to add my model to the admin.py file in blog folder.
```
from .models import Post

# Register your models here.
admin.site.register(Post)
```

#### User registration
The admin page is good for managing users, but if you are making an app for users accessing your site then you will need something more powerful.
The best is to create a new app for user logic accounts admin.
Update the settings.py with the name of your app.
Edit the views.py file with a new form. Django provide a form for user registration with `from django.contrib.auth.forms import UserCreationForm'
```
def register(request):
    if request.method == 'POST':
        form = UserCreationForm(request.POST)
        if form.is_valid():
            username = form.cleaned_data.get('username')
            messages.success(request, f'account created for {username}!')
            return redirect('blog-home')
    else:
        form = UserCreationForm()
    return render(request, 'users/register.html', {'form': form})
```

create a templates folder with users folder and register.html file. We gonna extend it with our existing template.
`{% csrf_token %}` is a security enhancement. It is needed!

```html
{% extends "blog/base.html" %}
{% load crispy_forms_tags %}
{% block content %}
    <div class="content-section">
        <form method="POST">
            {% csrf_token %}
            <fieldset class="form-group">
                <legend class="border-bottom mb-4">Join Today</legend>
                {{ form|crispy }}
            </fieldset>
            <div class="form-group">
                <button class="btn btn-outline-info" type="submit">Sign Up</button>
            </div>
        </form>
        <div class="border-top pt-3">
            <small class="text-muted">
                Already Have An Account? <a class="ml-2" href="#">Sign In</a>
            </small>
        </div>
    </div>
{% endblock content %}
```




[1]: <https://hg.python.org/cpython/file/tip/Lib/antigravity.py> "Hobbit lifestyles"
[2]: <https://forums.fast.ai/t/recommended-python-learning-resources/26888>
[3]: <https://www.python.org/downloads/>
[4]: <https://jupyter.org/install>
[5]: <https://nbviewer.jupyter.org/github/ipython/ipython/blob/master/examples/IPython%20Kernel/Index.ipynb>
[6]: <https://docs.djangoproject.com/en/3.0/ref/templates/builtins/#date>
