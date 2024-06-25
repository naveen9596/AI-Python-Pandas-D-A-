## 1.Introduction
Python
======
Python used on server to create web Applications
Guido Van Rossum-1991

##Why Python?
==========

-Simple syntax similar to English Lang
- Work on different Windows,linux,Mac
- python run on Interpreter System (line by line Execute).
- OOPS

##Python 2 & Python 3
=================
eg:
Input Method -python 3
Raw Input method -Python 2


PYTHON Syntax:
==============

##Python Variable:
ython Variables and Constants
In this session, you will learn about Python variables, constants, literals and their use cases.

number  = 90
number = 90
number = 9.1

. Python Variables
Note: In Python, we don't actually assign values to the variables. Instead, Python gives the reference of the object(value) to the variable.

Let us see valid variable names
firstname
lastname
age
country
city
first_name
last_name
capital_city
_if          # if we want to use reserved word as a variable
year_2021
year2021
current_year_2021
birth_year
num1
num2
Invalid variables names:

first-name
first@name
first$name
num-1
1num
Assigning values to Variables in Python
Example 1: Declaring and assigning value to a variable
number = 90
number = 9.1
number
9.1
website = "ap3-solutions.com"  # `website` is my variable and `ap3-solutions.com` is an argument
print(website)
ap3-solutions.com
Note: Python is a type-inferred language, so you don't have to explicitly define the variable type. It automatically knows that ap3-solutions.com is a string and declares the website variable as a string.

print('Hello',',', 'World','!') # it can take multiple arguments, 4 arguments have been passed
Hello , World !
first_name = 'AJANTHA'
last_name = 'DEVI'
country = 'INDIA'
city = 'CHENNAI'
age = 96
is_married = True
skills = ['Python', 'Matlab', 'JS', 'C', 'C++']
person_info = {
   'firstname':'AJANTHA',
   'lastname':'DEVI',
   'country':'INDIA',
   'city':'CHENNAI'
    }
Let us print and also find the length of the variables declared at the top:

# Printing the values stored in the variables

print('First name:', first_name)
print('First name length:', len(first_name))
print('Last name: ', last_name)
print('Last name length: ', len(last_name))
print('Country: ', country)
print('City: ', city)
print('Age: ', age)
print('Married: ', is_married)
print('Skills: ', skills)
print('Person information: ', person_info)
First name: AJANTHA
First name length: 7
Last name:  DEVI
Last name length:  4
Country:  INDIA
City:  CHENNAI
Age:  96
Married:  True
Skills:  ['Python', 'Matlab', 'JS', 'C', 'C++']
Person information:  {'firstname': 'AJANTHA', 'lastname': 'DEVI', 'country': 'INDIA', 'city': 'CHENNAI'}
Example 2: Declaring multiple variables in one line** using comma , and semicolon ;
a, b, c = 6, 9.3, "Hello"

print (a)
print (b)
print (c)
6
9.3
Hello
a = 1; b = 2; c = 3
print(a,b,c)  # outout: 1 2 3
a,b,c         # outout: 1 2 3
1 2 3
(1, 2, 3)
first_name, last_name, country, age, is_married = 'AJANTHA', 'DEVI', 'INDIA', 96, True

print(first_name, last_name, country, age, is_married)
print('First name:', first_name)
print('Last name: ', last_name)
print('Country: ', country)
print('Age: ', age) # Don't worry it is not my real age ^_^
print('Married: ', is_married)
AJANTHA DEVI INDIA 96 True
First name: AJANTHA
Last name:  DEVI
Country:  INDIA
Age:  96
Married:  True
If we want to assign the same value to multiple/chained variables at once, we can do this as:

x = y = z = "same"

print (x)
print (y)
print (z)
same
same
same
The second program assigns the same string to all the three variables x, y and z.

p = q = r = 300   # Assigning value together
print(p, q, r)    # Printing value together
300 300 300
Example 3: Changing the value of a variable
website = "ap3-solutions.com"
print(website)

# assigning a new variable to website
website = "google.com"

print(website)
ap3-solutions.com
google.com
In the above program, we have assigned ap3-solutions.com to the website variable initially. Then, the value is changed to google.com.

n=300
print(n)
300
m=n
print(n)

m = 1000   # assigning a new value to n
print(m)
300
1000
# Declare & Redeclare variables
m = "Python is Fun"
m = 10
print (m)
10
2. Constants
##Assigning value to constant in Python
Example 1: Declaring and assigning value to a constant
Note: In reality, we don't use constants in Python. Naming them in all capital letters is a convention to separate them from variables, however, it does not actually prevent reassignment.

PI=3.14
GRAVITY = 9.8
>>> import constant
>>>print(constant.PI)
>>>print(constant.GRAVITY)
  File "C:\Users\AJANTHA\AppData\Local\Temp/ipykernel_8264/698372323.py", line 2
    >>>print(constant.PI)
    ^
SyntaxError: invalid syntax
##Rules and Naming Convention for Variables and constants
The examples you have seen so far have used short, terse variable names like m and n. But variable names can be more verbose. In fact, it is usually beneficial if they are because it makes the purpose of the variable more evident at first glance.

Constant and variable names should have a combination of letters in lowercase (a to z) or uppercase (A to Z) or digits (0 to 9) or an underscore _. For example:
snake_case
MACRO_CASE
camelCase
CapWords
Create a name that makes sense. For example, vowel makes more sense than v.

If you want to create a variable name having two words, use underscore to separate them. For example:

my_name
current_salary
Use capital letters possible to declare a constant. For example:
PI
G
MASS
SPEED_OF_LIGHT
TEMP
Never use special symbols like !, @, #, $ % , etc.

Don't start a variable name with a digit.

Note: One of the additions to Python 3 was full Unicode support, which allows for Unicode characters in a variable name as well. You will learn about Unicode in greater depth in a future tutorial.

name = "Bob"
Age = 54
has_W2 = True
print(name, Age, has_W2)
Bob 54 True
1099_filed = False    # cannot start name of a variable with a number.
  File "C:\Users\AJANTHA\AppData\Local\Temp/ipykernel_8264/2261306508.py", line 1
    1099_filed = False    # cannot start name of a variable with a number.
        ^
SyntaxError: invalid decimal literal
age = 1
Age = 2
aGe = 3
AGE = 4
a_g_e = 5
_age = 6
age_ = 7
AGe = 8
print(age, Age, aGe, AGE, a_g_e, age, age, AGe)
1 2 3 4 5 1 1 8
