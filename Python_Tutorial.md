[TOC]
### Overview
Python is a high-level, interpreted, interactive and object-oriented scripting language. Python is degsigned to be highly readable. It use english keywords frequently where as other languages use punctuation, and it has fewer syntactial constructions than other languages.
#### Python environment variable
|path anme|description|
|:-------:|-----------|
|PYTHONPATH|It has role similar to Path. This variable tells the Python interpreter where to locate the module files importted into a program|
|PYTHONSTARUP|It contains the path of an initialization file containing python source code|
|PYTHONCASEOK|it is used in windows to instruct python to find the first case-insensitive match in an import statement.|
|PYTHONHOME|It is an alternative module search path.|
#### Python Identifiers
A Python identifier is a name used to identify a variable, funtion, class, module or other object. An identifier starts with a letter A to Z or underscore followed by zero or more letters, undersores and digits

Python does not allow punctuation characters such as @ and % within identifiers. Python is a case sensitive programming language.

Here are some naming conventions for Python identifier:

* Class Name start with an uppercase letter.
* Starting an identifier with a single leading underscore indicates that the identifier is private
* Starting an identifier with two leading underscores indicates a strongly private indetifier.
* If the indenfier alse ends with two trailing underscores, the identifier is a language-defined special name.

#### Lines and Indentation
Python provides no braces to indicate blocks of code for class and function definition or flow control. Blocks of code are denoted by line indentation, which is rigidly enforced.

The number of spaces in the indentation is variable, but all statements within the block must be indented the same amount.
#### Multi-Line statements
Statements in Python typically end with a new line. Python does, however, allow the use of the line continuation character (\\) to denote that the line should continue.
#### Quotation in Python
Python accepts single ('), double(") and triple(''' or """ ) quotes to denote string literals,.
The triple quotes are used to span the string across multiple line.
#### Comments in Python
A hash sign (#) that is not inside a string begins a comment. All characters after the # and up to the end of the physical line are part of the comment and the Python interpreter ignores them.
### Python Variable Types
Variables are nothing but reserved memory locations to store values. This means that when you create a variable you reserve some space in memeory.
#### Standard Data Types
Python has five standard data types

* Numbers
* String
* List
* Tuple
* Dictionary

#### Python Number
Python supports four different numerical types

* int(signed integers)
* long(long integers, they can also be represented in octal and hexadecimal)
* float(floating point real values)
* complex(complex numbers)

#### Python Strings

Stings in Python are identified as a congiguous set of characters represented in the quotation marks. Python allows for either pairs of single or double quotes. Subsets of string can be taken using the slice operator([] and [:]) with indexes starting at 0 in the beginning of the string and working their way from -1 at the end.

The Plus (+) sign is the string concatenation operator and the asterisk (*) is the repetition operator.

#### Python Lists
Lists are the most versatile of Python's compound data types. All the items belonging to a list can be of different data type.

The values stores in a list can be accessed using the slice operator with indexes starting at 0 in the beginning of the list and working their way to end -1. The plus(+) sign is the list concatenation operator, and the asterisk(*) is the repetition operator.

#### Python Tuples
A tuple is anoter sequence data type that is similar to the list. Unlike lists, however, tuples are enclosed with parentheses.

The main difference between lists and tuples is tupels cannot be updated. Tuples can be thought of as read-only lists.
#### Python Dictinary
Python's dictinaries are kind of hash table type. A dictionary key can be almost any python type, but are usually numbers or strings. Values, on the other hand can be any arbitary Python object.

Dictionaries are enclosed by curly brace and values can be assigned and accessed using square braces.

Dictionaries have no concept of order among elements.

#### Data Type Conversion
	int(x [,base])
	long(x [,base] 
	float(x)
	complex(real [,imag])
	str(x)
	repr(x)
	eval(str)
	tuple(s)
	list(s)
	set(s)
	dict(d)
	frozenset(s)
	chr(x)
	unichr(x)
	ord(x)
	hex(x)
	oct(x)
### Python Decision Making
Decision making is anticipation of conditions occurring while execution of program and specifying actions taken according to the condition.

Decision structures evalusate multiple expressions which produce true or false as outcome. You need to determine which ation to take and which statements to execute if outcome is true or false otherwise

Python programming language assumes any non-zero and non-null values are true, and if it is either zero or null, then is is assumed as false value

* if statements
	`
		if expression:
			statements(s)
	`	
* if...else statements
	`
		if expression:
			statements(s)
		else
			statements(s)
	`
* elif statements
	`
		if expression1:
			statements(s)
		elif expression2:
			statements(s)
		elif expression3:
			statements(s)
		else:
			statements(s)
	`

### Python Loops

* while loop
	`
	while expression:
		statements(s)
	`
* using else statement with loops
	`
	while expression:
		statements(s)
	else:
		statements

	`
* single statement suites
