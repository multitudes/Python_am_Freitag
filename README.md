# Python am Freitag

Introduction to Python
It is the material for a full week of Pithon.

Table of contents of the course:

[Installation](#Installation)  
[HelloWorld](#HelloWorld)  
[Variables](#Variables)  
[Variables](#Variables)  
[Variables](#Variables)  
[Variables](#Variables)  
[Variables](#Variables)  
[Some Humor](#Some Humor)

## Installation

Installation python 3.8, PyCharm IDE
Intro in the Python console, IDLE, PyCharm IDE.
Python basics: print hello world, work with variables, numbers (int, floats), strings , lists, tuples, dictionaries, loops (while, for ), functions,  read and write files to disks,  catch errors, import (internal and external packages), pip package manager, classes and objects, regex, internet sockets
Indentation is important. Indented 4 spaces 

## HelloWorld

Make a new file called hello.py and run it in terminal and in pycharm.. and in interpreter
```python
print("hello, world”)

```
“Hello World” is a constant or a string literal.
Python does not need curly braces, semicolons or to imports main etc. 
It works out of the box.

Different ways to print. We need no space after the hello if we use the comma variant.
```
answer = input("Name: ")
print("hello,", answer)
```

Another option is formatting the output. The syntax is:
```
answer = input("Name: ")
print(f"hello, {answer}")

planet = "world"
print("hello " + planet + "!")

print("hello " + planet.upper() + "\n")
```
Playing around:
```
print(planet.isascii())
print(planet.islower())

a = len(planet)
print(a)

print(planet[0])

print(planet.index("w"))
print(planet.replace("world", "er"))
```
link text itself

## Variables 
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

Numbers 
```
from math import *
print(str(2) + "my fav number")
a = -4
print(abs(a))
print(pow(2.3, 6))
print(max(4, 5))
print(min(4, 5))
print(round(5.4)) # up or down 
my_math = -5
print(sqrt(36))
print(floor(5.4))
print(ceil(5.4))
```
## Integers
```
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
```

## Floats



## Swap
```
# Swaps two integers
x = 1
y = 2
print(f"x is {x}, y is {y}")
x, y = y, x
print(f"x is {x}, y is {y}”)
```
In c for comparison:


## Boolean
```
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
```
s = input("Do you agree? \n ")

# Check answer
if s.lower() in ["y", "yes"]:
    print("\nagreed!")
elif s.lower() in ["n", "no"]:
    print(“no")
```

## Input
```
name = input("Enter your name: ")
age = input("Enter your age :")
print("\nhello " + name + "!")
print("You are " + age + “.")
```
There is a bug:
```
num1 = input("Enter a number : ")
num2 = input("Enter a number : ")
result = num1 + num2
print(result)
```
#### String interpolation
```
print('Hello %s!' % ('world'))
print('%s had %s pies.' % ('Alice', 42))
```

#### Strings
```
print(“????")

for i in range(4):
    print("?", end = “")

print("?" * 4)
```

Question if I print 4 blocks vertically what is the syntax to get rid of the last \n?
```
print(“#\n” * 4)
```

Use the end terminator ""

```
print("#\n" * 4, end=“")
```
Print a cat 
```
a = '''\    /\\
 )  ( ')
(  /  )
 \(__)|'''

print(a)
```
## Compare two strings
```
# Get two strings
s = input("s: ")
t = input("t: ")
# Compare strings for equality
if s == t:
    print("same")
else:
    print(“different”)
```

## Lists
List is a kind of collection.A list can contain any other python object. Uses square brackets
Can contain heterogeneous elements.
Lists are mutable. Strings are immutable.
Lists can be concatenated with plus
Range function returns a range of numbers excluding parameter. Range is an iterator in python3. Need to be converted to list
Start with empty list.. the ‘in’ and ‘not in’ operator. There is a sort() method
sorted() returns a new sorted list, leaving the original list unaffected. list.sort() sorts the list in-place, mutating the list indices, and returns None (like all in-place operations).

```
list()
print(list(range(6)))
print(list(range(1,6,2 )))

scores=[]
scores.append(72)
scores.append(73)
print(max(“hello”)
friends = ["Kevin", "Karin", "John", 2]
print(friends[2])
print(friends[-2])
print(friends[1:])
print(friends[1:3])
With strings, use “monty python” and slice
friends[1] = 22
print(friends[1])
numbers = [3, 4, 5, 6]
friends.extend(numbers) # extend is appending a list!
print(friends)
friends.append("joe")
friends.insert(2, “me")
print(friends.count(“joe”))
friends.remove("Kevin")
print(friends)
# friends.clear()
friends.pop()
print(friends.count("joe"))
friends.remove('me')
friends.remove('John')
friends.reverse()
print(friends)
print(friends.index(22))
friends.reverse()
friends.sort()
print(friends)
friends2 = friends.copy()
#join
a = ["a", "b", "c"]
print(“'".join(a))
```

## Condition 

```
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

## Loops
No do while loops in python!


#### Opportunity for better design
```
print("hello")
print("hello")
print(“hello")
```
#### Better design
```
for i in range(3):
    print("hello")
friends = ["joe", "tim", "luke"]
len(friends)
for friend in friends:
    print(friend)

for index in range(len(friends)):
    print(friends[index])

for i in range(3, 10):
    print(i)
for i in [3,4,5,6,7,8,9]:
    print(i)
```
```
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

++++ Aufgabe ++++++++

Ich habe diese message bekommen. Ich glaube es ist encrypted.
“dlrow olleh”. Schreib ein Programm um diese art von Nachrichten zu entziffern


#### Reverse Cipher
```
message = 'Three can keep a secret, if two of them are dead.'
translated = ''
i = len(message) - 1
while i >= 0:
    translated = translated + message[i]
    i = i - 1
print(translated)
```
+++++++++++++++++++++++++++++

#### Practice -  what does this code prints?
```
spam = 'foo'
for i in spam:
    spam = spam + i
print(spam)

print('f' not in ‘foo') # False

print('foo' in ‘f') # False

print(‘hello'.find('oo')) #-1
```

#### Comments 
```
'''
this is a comment
more comment
'''
# this too
```

Tuple are immutable
```
coordinates = (4, 5)
coordinates[0] = 11
# no changes supported in tuples they are immutable
print(coordinates)
```


++++++++++ exercise +++++++
```
def raise_to_power(base, power):
    result = 1
    for index in range(power):
        result = result * base
    return result

print(raise_to_power(3, 4))
print(raise_to_power(3, 5))
```
++++++++++++++++++++++++++++


## Abstraction

```
def main():
    for i in range(3):
        hello()
def hello():
    """hello once"""
    print(“hello")
if __name__ == "__main__":
    main()


# Abstraction with parameterization
def main():
    hello(3)
def hello(n):
    """hello some number of times"""
    for i in range(n):
        print("hello")
if __name__ == "__main__":
    main()

#extravagant!
print("hello\n" * 3)

Mario!
# Print out this many rows
for i in range(4):
    # Print out this many columns
    for j in range(4):
        print("#", end="")
    print()

Integer overflow!
from time import sleep
# Iteratively double i
i = 1
while True:
    print(i)
    i *= 2
    sleep(1)

floating point imprecision
x = float(input("x: "))
y = float(input("y: "))
z = x / y
#not integer overflow but floating point imprecision
print(f"x / y = {z:.50f}")
# print mit zero digits..
print(f"{sum2(10):.0f}")

Strings
s = input("Input: ")
print("Output:")
for c in s:
    print(c)

Iterate on characters
s = input("Input: ")
print("Output:", end="")
for i in range(len(s)):
    print(s[i], end="")

Uppercase 

s = input("Input: ")
print("Output:", end="")
print(s.upper())

c = 'p'
print("The ASCII value of '" + c + "' is", ord(c))
print(chr(65))

scores.append(33)
print(f"Averages: {sum(scores) / len(scores)}")

scores=[72, 73, 33]

line = "From laurent.brusa@me.com Sat Jan 5 09:15:55 2020"
words = line.split()
email = words[1]
email_pieces = email.split("@")



dictionary

Single quote are necessary in dict for the keys

No order! Imagine we use a look up tag! Init with dict()
Key value pairs
A common use is counting how many times we see something
It is an error to reference a key which is not in the dict
There is the “in” operator to check wether a key is in the dict 

counts = {}
pangram = "The quick brown fox jumps over the lazy dog"
for letter in pangram:
    if letter not in counts:
        counts[letter] = 1
    else:
        counts[letter] = counts[letter] + 1
print(counts)

Instead of checking if a key is already in the dic use get
counts = {}
pangram = "The quick brown fox jumps over the lazy dog"
for letter in pangram:
    counts[letter] = counts.get(letter, 0) + 1
print(counts)

A for loop going through the keys
for key in counts:
    print(key, counts[key])

Items are tuples!
print((counts.keys()))
print((counts.values()))
print((counts.items()))

for (key, value) in counts.items():
    print(key, value)

high_letter = None
high_count = None
for letter, count in counts.items():
    if letter == " ":
        continue
    if high_count == None or count > high_count:
        high_letter = letter
        high_count = count
print("The highest letter count is :",(high_letter, high_count))

Simple start ex
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


Tuples
Tuples are like lists, indexed at zero, can be iterated. Like strings are not modifiable.
Tuples can be sorted. We can sort dictionary using the items() 
y = (2,4,5,66)
for i in y:
    print(i)
print((max(y)))

(x,y) = (2, "Jo")
print(y)

print(sorted(counts.items()))

Sort by values. Create a list of tuples key value and invert and append
tmp = list()
for (key, value) in counts.items():
    tmp.append((value, key))
tmp = sorted(tmp)
print(tmp)

Shortest !
print(sorted([ (v,k) for k,v in counts.items() ]))

The ten top!
for value, key in tmp[:10]:
    print(key, value)



Functions 
def say_hi() :
    print("Hello")

print("top")
say_hi()
print("bottom")

def say_hi(name):
    print("hello" + name)

say_hi("steve")

Using the return statement
# This will not return nothing..
def cube(num):
    num * num * num

cube(2)

#need
def cube(num):
    return num * num * num

a = cube(2)
print(a)

Replace vowels or letters!
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


Try and except
Basic:

try:
    number = int(input("enter a number "))
    print(number)

except:
    print("Invalid")

better:

try:
    value = 10 / 0
    number = int(input("enter a number "))
    print(number)

except ZeroDivisionError as err:
    print("division by zero")
    print(err)

except ValueError:
    print("invalid input”)

Read and write io
Opening a file. The open() function returns a file handle
.read() is the whole string!
Use the mbox file:
fhand = open('mbox-short.txt')
for line in fhand:
    if line.startswith("From:"):
        print(line, end="")
# Or for the returns  
    line = line.rstrip()

Or better

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


text_file = open("text.txt", “r") # when “w” not readable!
print(text_file.readable())
text_file.close()

print(text_file.read())
print(text_file.readline())

Import

Make a file called useful.py
In the file put this function

import Random    
def roll_dice(num):
    return random.randint(1, num)

In a new file you call this function inserting the import on the top:
import useful_tools

print(useful_tools.roll_dice(10))


Check the docs for more modules!


Classes 

Create a student class in a file Student.py
class Student:
    def __init__(self, name, fach):
        self.name = name
        self.fach = fach

In dem anderen file:

from Student import Student
from Student import Question

student1 = Student(“jim","Business")

print(student1)
print(student1.name)
print(Student)

Constructor and deconstructor
Destructor is seldom used. Constructor is optional. 
class PartyAnimal:
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




Exercise : create a Frage class… for Quiz

ex:
question_prompts = ["What color are oranges? \n(a) orange \n(b) green\n”, "what color are bananas: \n(a) red\n(b) yellow\n"]
questions = [Question(question_prompts[0],"a"),
             Question(question_prompts[1], "b")]
def run_test(questions):
    score = 0
    for question in questions:
        answer = input(question.prompt)
        if answer == question.answer:
            score += 1
    print("you got a score of : " + str(score) + "/" +                      str(len(questions)) + " correct")

run_test(questions)

Inheritance
One file:
class Chef:

def make_chicken(self):
    print("I make chicken\n")

def make_salad(self):
    print("i can make salads! \n")

def make_special(self):
    print("here come a rib!")

Another file:

from Chef import Chef

class ChineseChef(Chef):

    def make_fried_rice(self):
        print("I make fried rice!")

    def make_special(self):
        print("here comes a duck!”)

Another file:

from Chef import Chef
from ChineseChef import ChineseChef

mychef = Chef()
mychef.make_chicken()
mychef.make_special()

myChineseChef = ChineseChef()
myChineseChef.make_fried_rice()
myChineseChef.make_special()
myChineseChef.make_chicken()


 
Get positive int

In Python the scope of a variable is the whole function

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




Command Line Arguments


Offset by one in python

from sys import argv
for i in range(len(argv)):
print(argv[i])
if len(argv) == 2:
    print(f"hello, {argv[1]}")
else:
    print("hello, world")

Exit with value:
from sys import argv, exit
if len(argv) < 2:
    print("missing command line argument \n")
    exit(1)
exit(0)

Array property ‘in’
from sys import exit
names = ['me', 'sarah', 'marco', 'steve']
name = input("name: ")
if name in names:
    print("\nFound")
    exit(0)
else:
    print("\nNot Found")
    exit(1)












File io

import csv
file = open("notebook.csv", "a")
name = input("name ")
phone = input("phone ")
writer = csv.writer(file)
writer.writerow((name, phone))
file.close()



or

import csv
name = input("name ")
phone = input("phone ")
with open("notebook.csv", "a") as file:
    writer = csv.writer(file)
    writer.writerow((name, phone))

Regular expression
See the quick guide
Need to import re, re.search() to match re.findall() to extract
Start with 
# Check answer
s = input("Do you agree? \n")
if s.lower() in ["y", "yes"]:
    print("\nagreed!")
elif s.lower() in ["n", "no"]:
    print("no")

And

import re
s = input("Do you agree? \n")
# Check answer
if re.search("yes", s):
    print("\nyes agreed!")
elif re.search("no", s):
    print("not agreed")
else:
    print("I do not know”)

Or change to 
if re.search("yes|y", s):

if re.search("y(es)?", s):

if re.search("y(es)?", s, re.IGNORECASE):

if re.search("^y(es)?$", s, re.IGNORECASE):

With emails. In mbox file
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

x = "My 2 favorite numbers are 42 and 19"
y = re.findall("[0-9]+", x)
print(y)

Greedy matching with * +

x = "From: using the colon again here : and see"
y = re.findall("^F.+:", x)
print(y)

\S is one non whitespace character
import re
fhand = open('mbox-short.txt')
text = fhand.read()
y = re.findall("From: (\S+@\S+)", text)
print(y)

\$ is one real dollar sign
x = "a real $10 bill"
y = re.findall("\$[0-9]+", x)
print(y)

More advanced

QR
import qrcode
#pip install qrcode
image = qrcode.make("https://youtu.be/oHg5SJYRHA0")
image.save("qr.png", "PNG")


Socket programming

“Tell me and I forget. Show me and I remember. Involve me and I understand.” 
Chinese proverb 
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

Server side
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

With urllib

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


#open the terminal below and enter python3 -m http.server 81
fhand = urllib.request.urlopen('http://0.0.0.0:81/pangram.txt')
for line in fhand:
    print(line.decode().strip())

Web scraping: Beautiful soup

import urllib.request, urllib.parse, urllib.error
from bs4 import BeautifulSoup
url = input("enter: ")
html = urllib.request.urlopen(url).read()
soup = BeautifulSoup(html, 'html.parser')
tags = soup('a')
for tag in tags:
    print(tag.get('href', None))

If error due to certificates

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

Serialise and deserialise with JSON and XML




# Words in dictionary
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


Speller

import re
import sys
import time

from dictionary import check, load, size, unload

# Maximum length for a word
# (e.g., pneumonoultramicroscopicsilicovolcanoconiosis)
LENGTH = 45

# Default dictionary
WORDS = "dictionaries/large"

# Check for correct number of args
if len(sys.argv) != 2 and len(sys.argv) != 3:
    print("Usage: speller [dictionary] text")
    sys.exit(1)

# Benchmarks
time_load, time_check, time_size, time_unload = 0.0, 0.0, 0.0, 0.0

# Determine dictionary to use
dictionary = sys.argv[1] if len(sys.argv) == 3 else WORDS

# Load dictionary
before = time.process_time()
loaded = load(dictionary)
after = time.process_time()

# Exit if dictionary not loaded
if not loaded:
    print(f"Could not load {dictionary}.")
    sys.exit(1)

# Calculate time to load dictionary
time_load = after - before

# Try to open text
text = sys.argv[2] if len(sys.argv) == 3 else sys.argv[1]
file = open(text, "r", encoding="latin_1")
if not file:
    print("Could not open {}.".format(text))
    unload()
    sys.exit(1)

# Prepare to report misspellings
print("\nMISSPELLED WORDS\n")

# Prepare to spell-check
word = ""
index, misspellings, words = 0, 0, 0

# Spell-check each word in file
while True:
    c = file.read(1)
    if not c:
        break

    # Allow alphabetical characters and apostrophes (for possessives)
    if re.match(r"[A-Za-z]", c) or (c == "'" and index > 0):

        # Append character to word
        word += c
        index += 1

        # Ignore alphabetical strings too long to be words
        if index > LENGTH:

            # Consume remainder of alphabetical string
            while True:
                c = file.read(1)
                if not c or not re.match(r"[A-Za-z]", c):
                    break

            # Prepare for new word
            index, word = 0, ""

    # Ignore words with numbers (like MS Word can)
    elif c.isdigit():

        # Consume remainder of alphanumeric string
        while True:
            c = file.read(1)
            if not c or (not c.isalpha() and not c.isdigit()):
                break

        # Prepare for new word
        index, word = 0, ""

    # We must have found a whole word
    elif index > 0:

        # Update counter
        words += 1

        # Check word's spelling
        before = time.process_time()
        misspelled = not check(word)
        after = time.process_time()

        # Update benchmark
        time_check += after - before

        # Print word if misspelled
        if misspelled:
            print(word)
            misspellings += 1

        # Prepare for next word
        index, word = 0, ""

# Close file
file.close()

# Determine dictionary's size
before = time.process_time()
n = size()
after = time.process_time()

# Calculate time to determine dictionary's size
time_size = after - before

# Unload dictionary
before = time.process_time()
unloaded = unload()
after = time.process_time()

# Abort if dictionary not unloaded
if not unloaded:
    print(f"Could not load {dictionary}.")
    sys.exit(1)

# Calculate time to determine dictionary's size
time_unload = after - before

# Report benchmarks
print(f"\nWORDS MISSPELLED:     {misspellings}")
print(f"WORDS IN DICTIONARY:  {n}")
print(f"WORDS IN TEXT:        {words}")
print(f"TIME IN load:         {time_load:.2f}")
print(f"TIME IN check:        {time_check:.2f}")
print(f"TIME IN size:         {time_size:.2f}")
print(f"TIME IN unload:       {time_unload:.2f}")
print(f"TOTAL TIME:           {time_load + time_check + time_size + time_unload:.2f}\n")

# Success
sys.exit(0)


Pillow

This is the blur effect

from PIL import Image, ImageFilter

before = Image.open("Mushroom.png")
after = before.filter(ImageFilter.BLUR)
after.save("out.png")


Exercises


CS50 problems 
mario/ cash / credit cards/cesar / crack / vigenere / bleep

Mario
n = 8
a: int = n
b: int = 0
for i in range(n):
    a = a - 1
    b = b + 1
    print("." * a, end="")
    print("x" * b, end="\n")

Both sides
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

Print a cat



Three Questions Quiz
Can be done in many different ways, 
with if statements. 
With reading from file
With lists / dicts
With oop

The Captcha:
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

Python program for implementation of Bubble Sort

def bubbleSort(arr):
    n = len(arr)
    # Traverse through all array elements
    for i in range(n):
        # Last i elements are already in place
        for j in range(0, n - i - 1):
            # traverse the array from 0 to n-i-1
            # Swap if the element found is greater
            # than the next element
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
# Driver code to test above
arr = [64, 34, 25, 12, 22, 11, 90]
bubbleSort(arr)
print("Sorted array is:")
for i in range(len(arr)):
    print("%d" % (arr[i]), end=", ")



A List of Python Resources:

Beginners to programming
Whirlwind Tour of Python 4.3k Nice only book that covers all the essential Python basics without overwhelming the Python novice.
Learn Python the Hard Way 1.7k: widely used book for learning Python as a first programming language
Automate the boring stuff with Python by Al Sweigart 1.1k: Contains a lot of scripts to make your boring task easier.
Python tutorials by Sentdex 883: This website contains everything related to python from beginner to advance level
Python OOP’s tutorial by Corey Schafer 1.1k : OOP concepts in python, which are extensively used in pytorch.
Real Python 358 - A curated list of (long) blog posts on various aspects of Python programming from language fundamentals to advanced concepts, with applications along the way.
Udemy complete python bootcamp: Go from zero to hero in Python 3 545: (paid usually available for around $19) video and notebook based course that starts from the basics of Python and builds a few small milestone projects along the way.
Learn to Program with Python 610: (video course) Full multipart introduction to programming with python by Derek Banas (free).
Introducing Python 389 - Excellent book with lots of examples, also introducing the python ecosystem and useful packages.
Solo Learn 352: This app is good for beginners and gives you the game like feeling.
Code academy 359: Good for beginners as it contains exercise also which will help you to learn quickly
Python - The No Theory Guide 763: Collection of Jupyter Notebooks that help you learn Python with hands-on Programming.
Introduction to Computer Science and Programming Using Python 1.5k: This is a really good course, and recommended by a good number of folks from the Reddit Python community
Intermediate programmers
The Hitchhiker’s Guide to Python 980: a book on Python from Kenneth Reitz, the author of requests library. A comprehensive introduction into Python’s eco-system and best practices.
Peter Norvig’s Pytudes 604: a github repo that contains well-made jupyter notebooks, ranging in topics from Gesture Typing 74 to A Concrete Introduction to Probability (using Python) 237. These notebooks make for some great reads and the coding style is a good resource to learn from, especially in ways of breaking down problems in clear, readable code.
Design of Computer Programs 388 also by Peter Norvig on Udacity is a great programming course in general, and has good introductions to comprehensions and generators.
Fluent Python 462: introduces the internals of python, helps you write more pythonic code.
Derek Banas - Python in one video 296 : Ideal for people that have experience in some other programming language and want a quick tour of python
Trey Hunner 118: Trey has done a lot of webcasts as well as written a lot of good article focusing on intermediate python developer.
Python tricks by Dan bader 266: This book contains a lot of tricks which will make you a great Pythonista, you can also follow dan’s personal website https://dbader.org/ 117 to learn more about the python tips and tricks.
Google’s Python Class 300:Google’s Python Class is a short but great introduction to python for people who already know programming but are new to python. It is available both as video lectures and articles.
Advanced programmers (but maybe new to python)
Learn x in y minutes 1.2k: quick overview of main Python 3 features entirely using code examples
David Beazley’s courses, tutorials, and books 593: generators, yields, descriptors, and other advanced topics
Raymond Hettinger 742: If you want to master python skills then Raymond is the man, he has been a python core developer for many years and tend to give an advance talk.
Python numeric programming (for people that know python already)
Stanford numpy tutorial 737: great little intro to key python libs and concepts for numeric programming
Python Data Science Handbook 489 (by Jake VanderPlas) - An introduction to the major scientific Python/“PyData” packages and best practices. (Being two years old it may be slightly dated (only slightly) at a few places in terms of the API used, but it’s still a great intro and reference.) [The author has generously made available the entire book as freely available notebooks; however the book can also be purchased 16 in print and electronic formats.]
Python for data science by wes mckinney(author of pandas) 531: The author of pandas himself starts from basics and goes to advance features of pandas. In short great material to start learning pandas.
Python challenges
https://codechalleng.es/challenges/ 696 - It’s good if you are just starting with python
CheckIO 453 - Go on an (game) adventure by solving programming challenges with Python.
Python podcast
https://talkpython.fm/ 493 - you will fall in love with python after watching this podcast
https://pythonbytes.fm/ 104 - This podcast will keep you updated about the python community and new.
Python Newsletters
If you want to keep updated with the python articles, videos and more then subscribe to these channels
https://www.pythonweekly.com/ 147
https://importpython.com/newsletter/ 74
https://pycoders.com/ 

And curl! For windows! (check Cygwin
https://curl.haxx.se/download.html


Algorithms

The big O. To compare algorithms, which one is better than other.
Speed, and size with memory. Micro 10 to -6 and nano to -9
For loops are slow!
We compare how quickly the runtime grows not the actual time. In the first function it grows 
proportionally to n + 1. For big numbers the “+1” is irrelevant so we just say O(n)
Asymptotic analysis. In math describing limiting behaviour
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

## Some Humor

https://www.xkcd.com/323/
Bac blood alcohol content

https://projekteuler.de

https://projecteuler.net/problem=1

If Python is executable pseudocode then Perl is executable line noise..
https://www.youtube.com/watch?v=zJOS0sV2a24

#### [Antigravity][1]

```
```




[1]: <https://hg.python.org/cpython/file/tip/Lib/antigravity.py> "Hobbit lifestyles"
