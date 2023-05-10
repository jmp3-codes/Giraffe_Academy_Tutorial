## Variables and Data Types
Python executes things in order starting from line 1

Variable - container where we can store certain data values. 
Putting it in a container makes it easier to manipulate variables

### Assigning variables
`variable_name` = "some string"

Variables can be also be modified and updated

`variable_name` = "some new string"

### Data Types
String - plain text; requires quotation marks

Number - can use whole or decimal numbers

Boolean value - value that is True or False (must be capitalised)

## Working with Strings
`\n` - creates new line 

`  \  ` is escape character. Means that python will interpret whatever is after
literally 

Can store string values inside variables

    phrase = "Giraffe Academy"
    print(phrase)

Concatenation - process of taking a string and appending another string onto it, uses `  +  `

### Common String Functions 

Can use functions to modify strings and get info about them

Can access them by calling the string variable with `  .  ` after

    print(phrase.lower()) -- lower case
    print(len(phrase)) -- length of string
    print(phrase[3]) -- grab the chracter of whatver is in the square bracket
    print(phrase.index("G")) -- grab the index of the character
    print(phrase.replace()) - can replace str, passes 2 arguments
*Note* 
In python index for strings starts at 0

## Working with Numbers
Python follows order of operations

% (modulus operator) - gives the remainder

`str(my_num)` - converts number to string. Need this if you want to print out a number next to a string

### Common number functions

`abs` find absolute value

`pow` raise to power

`min/max` - which of the numbers is min/max

`round` - 

A lot of the other functions are in the math module 

    from math import *

`floor` - rounds down no matter what

`ceil` - rounds up 

`sqrt` - square root

## Getting Input from Users

`input("Prompt for User")`

*Example*
    
    name = input("Enter Your Name: ")
    
    age = input("Enter Your Age: ")
    
    print("Hi " + name + "! You are " + age)

## Building a simple calculator 

When we get input from a user, by default python is going to convert it to a string 
So we need to convert them to numbers

2 possible functions:
`int`
`float`

*Basic Calculator*

    num1 = input("Enter a number: ")
    num2 = input("Enter another number: ")
    result = float(num1) + float(num2)
    
    print(result)

## Mad Libs Game

Game where you prompt user for list of words to substitute
for blanks into a story

Example

    color = input("Enter a color: ")
    plural_noun = input("Enter a plural noun: ")
    celebrity = input("Enter a celebrity: ")
    
    print("Roses are " + color)
    print(plural_noun + " are blue")
    print("I love " + celebrity)

## Lists

Lists are a type of data structure.
**data structures** are containers that store different values

Lists are a structure that stores lists of information.
Can take and keep track of related data values.

Lists are written with square brackets [ ]

Values are stored into the same variable, and then you can access
the list items from within that variable 

Can access the different items in the list using their index.
*Index starts at 0.*
Can specify a range with the index

    friends = ["Kevin", "Karen", "Jim"]
    print(friends[1:])

*Note; When you specify a range, it will grab everything
from the first index up to, **but not including** the last* 

Can update individual elements inside the list
    
    friends[1] = "Mike"

### List Functions

`list.extend(list2)` Allows you to append another list

`list.append("new_item")` Add new elements to list *(automatically added to the end)*

`list.insert(position, "new_item")` Add new item to list in specific position

`list.remove("existing_item")` Remove element from list

`list.clear()` Remove all elements from list

`list.pop()` removes last element from list

`list.index(item)` Give index of an item in the list. If item not in the list passes an error 

`list.count("item")` Gives count of item in the list

`list.sort()` Sorts list into ascending alphabetical/numerical order

`list.reverse()` Reverses list

`list.copy()`   Creates copy of list

## Tuples

Tuples are another type of container. It is a collection that is ordered and immutable 

Tuples are written with round brackets (  )

Can access elements inside the tuple using index [  ]

### Differences between tuples and lists

Useful to store data that doesn't/can't be mutated inside tuples
eg. coordinates

## Functions

Functions are blocks of code. Help you break up code into useful tasks or functions

`def new_fx():` used to create a function

Code for the fx will be indented.
To execute code in the fx, you have to call it 

**General Practice**

1. Functions all lower case
2. Underscore between words
3. Use functions for group of code that's designed to perform a specific task

Can give fx's parameters (piece of info we give to the fx)
    
    def say_hi(name,age):
        print("Hello " + name + ", you are " + age)

    say_hi("Mike", "35")
    say_hi("Steve", "70")

### Return Statement

Allows us to return info or get values back from a fx 
e.g. telling us how the task went or giving the result of the fx

**Note** Return breaks us out of the fx, nothing after it is executed

    def cube(num):
        return num*num*num

    result = cube(4)    
    print(result)

## If...Else Statements

Allows program to respond to input 

`if` - execute code *if* the statement is true or conditions are met

`elif` - else if... used to check another condition

`or` and `and` - used to combine several conditional statements

`not(variable)` - will negate the variable

### If statements and comparisons 

Python comparison operators:
==, !=, >, <, >=, <=

Can compare numbers, strings, lists etc.

    # Create fx that prints biggest number from a list that we pass it
    # Takes 3 parameters

    def max_num(num1, num2, num3):
        if num1 >= num2 and num1 >= num3:
            return num1
        elif num2 >= num1 and num2 >= num3:
            return num2
        else:
            return num3

    print(max_num(28,4,77))

## Building a better calculator 

    num1 = float(input("Enter first number: "))
    op = input("Enter operator: ")
    num2 = float(input("Enter second number: "))

    if op == "+":
        print(num1+num2)
    elif op == "-":
        print(num1-num2)
    elif op == "/":
        print(num1/num2)
    elif op == "*":
        print(num1*num2)
    else:
        print("Invalid Operator")

Used if/else statements to figure out what the user wanted to do

## Dictionaries

Dictionaries are another type of container. 
It is a collection which is ordered and mutable.

**NB** *Dictionaries store key-value pairs*

Dictionaries are written with {key1:value1,key2:value2...}

**NB** *Each key has to be unique*

`dictionary[key]` will return value for that key

`dictionary.get(key, default value)` does the same, but passes default value if key not in the dictionary

## While Loop

`while condition` allows us to loop through and execute a block of code multiple times

Will loop through the code associated with `while` until the condition is false

+= adds number to a variable, and assigns the result to the variable

`i += 1` is shorthand for `i = i + 1`

Works similarly for other operators ( - , / , * )


## Building A Guessing Game

Users passes a word, trying to guess the secret word. 
They have 3 guesses, otherwise they lose the game.

    secret_word = "giraffe"
    guess = ""
    guess_count = 0
    guess_limit = 3
    out_of_guesses = False
    
    
    while guess != secret_word and not(out_of_guesses):
        if guess_count < guess_limit:
            guess = input("Enter guess: ")
            guess_count += 1
        else:
            out_of_guesses = True
    
    if out_of_guesses:
        print("Out of Guesses, YOU LOSE")
    else:
        print("You win!")

## For Loops

`for` used to iterate over a sequence/collection (list,tuple,dictionary,set or string)

    friends = ["Jim", "Karen", "Kevin"]
    for friend in friends:
        print(friend)

## Exponent Function

    def raise_to_power(base_num, pow_num):
        result = 1
        for index in range(pow_num):
            result = result * base_num
        return result
    
    print(raise_to_power(3,4))

## 2D Lists and Nested Loops 

Can make a list of lists. Using 2D lists we can create a grid-like structure inside of python:
1. Each list acts as a row.
2. Each item within that list/row is a column.

Can access elements within the 2D list by calling:

`list[row index][column index]`

Example:
    
    number_grid = [
        [1, 2, 3], #row 0
        [4, 5, 6], #row 1
        [7, 8, 9], #row 2
        [0]
    ]
    
    print(number_grid[2][1])
    
    Output -- 8

Can parse through this 2D list using nested for loop

    for row in number_grid:
        for column in row:
            print(column)

## Building a Basic Translator 

Create a language where vowels are changed to G

    def translate(phrase):
        translation = ""
        for letter in phrase:
            if letter.lower() in "aeiou":
                if letter.isupper():
                    translation = translation + "G"
                else:
                    translation = translation + "g"
            else:
                translation = translation + letter
        return translation
    
    print(translate(input("Enter a phrase: ")))

## Try/Except

When an error or exception occurs, python stops and generates an error message.
We can handle these exceptions using try/except.
Useful for helping to account for user input errors.

`try` - lets you test a block of code for errors

`except` - lets you handle the error

We can also handle specific types of errors.
Specify what happens when certain things break.
Good practice is to use except to catch specific errors.
Just using except alone is too broad.

`except error_name`

Can use this to print out the specific error 

    except some_error as err:
        print(err)

## Reading from external files

Opening files in python:
`open(file_name, mode)`

For file name, you can provide either a:
1. Relative path to file
2. Absolute path to file
3. File name if file is in the same directory as .py

For mode, you can pass either:
"r" - read only;
"w" - write (can modify the file);
"a" - can append info to file (but can't modify existing info);
"r+" - read and write

Generally we want to store opened files inside a variable.

Want to check that the file is readable. Fx returns a boolean value:
`print(opened_file.readable())`

**NB**: Once you've opened the file you want to make sure that at some point you close the file.
Can use:
`opened_file.close()`

Useful read functions:

`opened_file.read()`

`opened_file.readline()`

`opened_file.readlines()` - will put each line inside a list.

Can use this in combination with for loop to write out each line in the file:

    employee_file = open("employees.txt", "r")
    for employee in employee_file.readlines():
        print(employee)

## Writing to and Appending Files

Need to be careful with appending and be very specific

`opened_file.write("New text")`

To make sure that it gets added on a new line need to add `\n`

When you are in write mode:
`opened_file.write()`
will overwrite everything in the existing file

You can also use `.write` in write mode to create new files

## Modules and Pip

Module is essentially a python file that we can import into our current python file.

If .py file is in the same directory:

`import file_name`

Then you can call functions and variables from the module that you imported.

`file_name.function()`

Python module index - contains list of pre-configured python modules.
There's also lots of 3rd party modules - contain tools for variety of applications.

### Pip

**Pip** is a package manager - comes preinstalled on python3.
Can use it to install 3rd party modules

## Classes and Objects

Python is an object-oriented programming language. 
Almost everything in Python is an object, with associated properties and methods.
A **class** is an object constructor. So it defines the object type. 
It is a template or blueprint for creating particular kinds of objects.

We can use classes and objects to model real world objects and create our own data types.

`class New_Class:`

### Init Function

We can then define attributes for this new class below using the initialize fx.
All classes have a fx called `__init__(  )` which is always executed when the class is being initiated.

`def __init__(self,attributes):`

Example; creating a student data type:
    
    class Student:

        def __init__(self, name, major, gpa, is_on_probation):
            self.name = name
            self.major = major
            self.gpa = gpa
            self.is_on_probation = is_on_probation

The init function assigns the values that we pass in to the 
attributes of the object that we are creating.

e.g. the name attribute of the student object = the name that we are passing in

We can then import this class from the associated file and create an object from this new class.
So when we do:
    
    from student (the file) import Student (the class)
    student1 = Student("Jim", "Business", 3.1, False)

It's taking the information that we're passing it and storing it as attributes for the object. 

Once we've created the object, we can then access the attributes of the object:

`object1.Class_attribute`

## Building a Multiple Choice Quiz

*We are building a multiple choice quiz that keeps track of a user's score*

How to represent the questions?
Need to keep track of the question/prompt, and answer. So 2 attributes to keep track of.
Best way to do this is to create a question class

    class Question:
        def __init__(self, prompt, answer):
            self.prompt = prompt
            self.answer = answer

    from question import Question
    question_prompts = [
        "What color are apples?\n(a) Red/Green\n(b) Purple\n(c) Orange\n\n",
        "What color are bananas?\n(a) Teal\n(b) Magenta\n(c) Yellow\n\n",
        "What color are strawberries?\n(a) Yellow\n(b) Red\n(c) Blue\n\n"
    ]
    
    questions = [
        Question(question_prompts[0], "a"),
        Question(question_prompts[1], "c"),
        Question(question_prompts[2], "b"),
    ]

    def run_test(questions):
        score = 0
        for question in questions:
            answer = input(question.prompt)
            if answer == question.answer:
                score += 1
        print("You got " + str(score) + "/" + str(len(questions)) + " correct")
    
    run_test(questions)

Good thing with this is that we can easily add new questions. 

Alter the quiz so that it has a 4th question, and can handle upper or lower case inputs.
Print the well done if answer is correct, or say the correct answer if wrong.
Also print a message at the end based on the user's score.

    from question import Question
    question_prompts = [
        "What color are apples?\n(a) Red/Green\n(b) Purple\n(c) Orange\n\n",
        "What color are bananas?\n(a) Teal\n(b) Magenta\n(c) Yellow\n\n",
        "What color are strawberries?\n(a) Yellow\n(b) Red\n(c) Blue\n\n",
        "What color are oranges?\n(a) Red/Green\n(b) Purple\n(c) Orange\n\n"
    ]
    
    questions = [
        Question(question_prompts[0], "a"),
        Question(question_prompts[1], "c"),
        Question(question_prompts[2], "b"),
        Question(question_prompts[3], "c")
    ]

    def run_test(questions):
        score = 0
        for question in questions:
            answer = (input(question.prompt)).lower()
            if answer == question.answer:
                score += 1
                print("Correct. Well done!\n")
            else:
                print("The correct answer is: " + question.answer)
        print("\n\nYou got " + str(score) + "/" + str(len(questions)) + " correct")
        if score >= 3:
            print("\nWell done!")
        else:
            print("\nTry again.")
    
    run_test(questions)

## Object Functions

We can use functions inside classes. 
All objects of that class can then access the function. 

Using our student class:

    class Student:
    
        def __init__(self, name, major, gpa):
            self.name = name
            self.major = major
            self.gpa = gpa
    
        def on_honor_roll(self):
            if self.gpa >= 3.5:
                return True
            else:
                return False

    student2 = Student("Phyllis", "Business", 3.8)
    
    print(student2.on_honor_roll())
    "True"

## Inheritance

Inheritance is where we can define attributes and fx's inside a class, 
then we can create another class and inherit all those attributes.

Allows us to inherit functionality from an existing class into a new class.

To inherit:

    from file import Existing_Class

    class NewClass(Existing_Class)

The `NewClass` will now have all the attributes of the `Existing_Class`.
We can also override any existing attributes with new `def` statements



