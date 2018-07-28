---
layout: post
title: "Python: Basic Types, Syntax, and Operations"
categories: programming learning python
---

<div class="section" id="structure">Structure</div>

<p>
As mentioned earlier, Python delimits code struture with whitespace. Statements
are separated with newlines rather than semicolons, and new blocks are
designated with 
<a href="https://www.python.org/dev/peps/pep-0008/#indentation" target="_blank">
indentation.</a>
{% highlight python %}
# Comments start with a hash
my_var = 1

# if block shown by indentation
if my_var == 0:             
    print("Hello!")         

# End of if shown by return to normal indentation levels
print("Goodbye!"){% endhighlight %} 
The above code prints only "Goodbye!" to standard output. Continuation of
statements broken up over multiple lines is done by a '\' immediately followed
by a newline. Code within '(', '{', and '[' is automatically continued across
newlines. Semicolons may be used to delimit multiple statements
placed on the same line. Preferred style should be read from 
<a href="https://www.python.org/dev/peps/pep-0008/" target="_blank">
PEP8.</a>
{% highlight python %}
# Multiple statements on one line with semicolons
x = 1; y = 2; z = 3

# Line continuation within parenthesis  
if (x == 1 and 
    y == 2): 
    print("Hello!")

# Line continuation with backslash 
n = (x + y + z) * \
    y + z{% endhighlight %} 
</p>


<div class="section" id="types">Types and Objects</div>

<p>
Python is a 
<a
href="https://pythonconquerstheuniverse.wordpress.com/2009/10/03/static-vs-dynamic-typing-of-programming-languages/"
target="_blank">
dynamically and strongly typed</a> language. All variables are objects, 
including variables pointing to integers, booleans,
and other types which may be familiar as primitives. Unlike pointers in C or
references in Java, variable names in Python do not have a type, and
names can be reassigned to unrelated objects. Types are bound to values, or
objects, rather than
to variable names (dynamic typing). However, operations on unrelated
types aren't permitted without explicit casting (strong typing). 
{% highlight python %}
my_var = 5              # Assigning an integer to my_var
my_var = "Five"         # Reassigning my_var to a string

other_var = 10 
print(my_var + other_var)   # Error thrown! Unrelated types {% endhighlight %}
</p>


<p>
Integers and floating point numbers may be operated on with
standard arithmetic operators. There are no distinctions between longs and ints,
and ints are 
<a
href="https://www.geeksforgeeks.org/what-is-maximum-possible-value-of-an-integer-in-python/"
target="_blank">unbounded</a> in maximum value, restricted only by available memory.
{% highlight python %}
x = 3.0             # Assigning a floating point
y = 10              # Assigning an integer

z = x + y           # Addition, z = 13.0
z = x - y           # Subtraction, z = -7.0 
z = x * y           # Multiplication, z = 30.0
z = y % 3           # Modulus, z = 1

z = y / 3           # Standard division, z = 3.333 ... 
z = y // 3          # Truncated division, z = 3
z = y // 3.0        # Truncated division, z = 3.0
z = y ** x          # Exponentiation, z = 1000.0{% endhighlight %}
Notice that operations between floating points and integers return
floating points, even in the case of truncated division. Integer division done
with the '/' operator will also return floating points. The '//' operator must be used
between two integers to return an integer. Operations follow standard arithmetic
precedence, with parenthesis binding lower precedence operators. 
</p>


<p>
Floating points, integers, and bools may be converted between one
another using type conversion functions. Bools are assigned values of
upper-cased True or False. 
{% highlight python %}
my_bool = True
x = int(my_bool)    # x = 1

my_bool = False
y = float(my_bool)  # y = 0.0

x = 100
my_bool = bool(x)   # my_bool = True
my_bool = bool(y)   # my_bool = False{% endhighlight %}
</p>


<p>
Singular types of byte, short, and long are unified under integer types. Float
and double are unified under floating point types. Null is roughly equivalent to
upper-cased 
<a href="https://www.pythoncentral.io/python-null-equivalent-none/"
target="_blank">None</a>. None is an object of type NoneType rather than a
value. The built in function of 
<a href="https://docs.python.org/3/library/functions.html#type" target="_blank">
type()</a>
may be used to return the type of an object. 
{% highlight python %}
bar = 5 
type(bar)           # <class 'int'>

bar = 5.
type(bar)           # <class 'float'>

bar = True
type(bar)           # <class 'bool'>

bar = None
type(bar)           # <class 'NoneType'>{% endhighlight %}
</p>


<p>
The built in function 
<a href="https://docs.python.org/3/library/functions.html#id" target="_blank">
id()</a> returns the memory address of an object (for CPython). This can be used
to demonstrate immutability and referencing. The covered types of
bool, int, and float are immutable, and reassignment of variable names creates
new objects. Try the following on your terminal; memory addresses will vary.
{% highlight python %}
foo = 5             # new int object created
id(foo)             # 4372930720 

foo = 10            # new int object created
id(foo)             # 4372930880

foo = True          # new bool object created
id(foo)             # 4372526608{% endhighlight %}


The comments of object creation are not precisely true - integers in the
range of [-5, 256] are cached, along with bool objects. For the above example,
the variable name of foo can be thought to be reassigned to existing objects.
</p>


<p>
The built in 
<a href="https://docs.python.org/3/library/functions.html#hex"
target="_blank">hex()</a> function will convert an integer to its hexadecimal
representation. Notice the following variable names refer to the same object in
memory. 
{% highlight python %}
foo = 10
bar = 10

# These variables refer to the same object
hex(id(foo))        # 0x1049a0140
hex(id(bar))        # 0x1049a0140

foo = 300
# foo refers to newly created int object
hex(id(foo))        # 0x104c16f70{% endhighlight %}

These optimizations are not guaranteed, particularly for larger integers and complex objects.
As expected, all objects are placed on a 
<a href="https://docs.python.org/3/c-api/memory.html" target="_blank">private heap</a>,
and garbage collection of unreferenced objects is automatic. Size of
objects may vary based on implementation, but integers are often at least 28
bytes, far larger than most other language's 4 or 8 bytes. This reflects that
they are complete objects with various attributes. 
</p>


<p>
String types have a variety of 
<a href="https://docs.python.org/3/library/stdtypes.html#string-methods"
target="_blank">methods</a> (member functions). Variables can be assigned using
single, double, or 
<a href="https://developers.google.com/edu/python/strings" target="_blank">triple quoted</a>
strings. There is no difference between single
and double quotes. Triple quotes preserve whitespace, including newlines.
Standard escapes apply with '\'. Type conversion is done with the str()
function.
{% highlight python %}
# Single quoted string, double quote internally without escape
string1 = 'That\'s when he said, "Hello, World!"'

# Double quoted string, single quote internally without escape
string2 = "That's when he said, \"Hello, World!\""

string1 == string2  # True

# Type conversion for strings 
x = 5               # x is an int type 
string4 = str(x)   
type(string4)       # <class 'str'>
string4             # '5'
{% endhighlight %} 

Strings are concatenated with '+' and repeated with '*'. There is no singular
char type; strings of length 1 are extracted with '[]'. Negative indices
correspond to the last character. Length of strings is returned from the 
<a href="https://docs.python.org/3/library/functions.html#len"
target="_blank">len()</a>
function. Strings are immutable. Characters at indices cannot be reassigned. 
{% highlight python %}
s1 = "Learning!"

s2 = s1[0]          # s2 = "L"
s2 = s1[-1]         # s2 = "!"
s2 = s1[-3]         # s2 = "n"
s2 = s2 * 5         # s2 = "!!!!!"
s2 = s1 + s1        # s2 = "Learning!Learning!"

s1_length = len(s1) # s1_length = 9

s1[0] = "B"         # Error thrown! Strings are immutable
{% endhighlight %}
</p>

<p>
Slicing is accomplished with '[<i>start</i> : <i>end</i> : <i>step</i>]', and
returns substrings. Indices are inclusive-exclusive of start-end, as
[<i>start</i>, <i>end</i>). Empty start or end is inferred as beginning or
end of string. Negative step allows for backwards iteration, beginning at start
index; omitting step infers step of 1. 

{% highlight python %}
s1 = "UCSD2020"

s2 = s1[0:]         # s2 = "UCSD2020"
s2 = s1[:-1]        # s2 = "UCSD202"
s2 = s1[1:-2]       # s2 = "CSD20"

s2 = s1[::-1]       # s2 = "0202DSCU"
s2 = s1[3::-1]      # s2 = "DSCU"
s2 = s1[1:8:2]      # s2 = "CD00"
{% endhighlight %}
</p>

<p>
The following are 
<a href="https://docs.python.org/3/library/stdtypes.html#string-methods"
target="_blank">methods</a> 
called on string variables. Method split() breaks a string into substrings
across a passed delimiter, defaulting to whitespace. Substrings are stored in a
list, a data structure covered in the following section. Methods
upper() and lower() return upper- or lower-cased strings. New strings are
returned and must be assigned due to string immutability. Some bool returning
methods are isalnum() for alphanumeric characters, isalpha() for alphabetic
characters, islower() for lower-case, isupper() for upper-case, and isspace()
for whitespace only. 
{% highlight python %}
s1 = "Thus, we conclude, henceforth, this sentence is long."
list = s1.split(",")
list
# ['Thus', ' we conclude', ' henceforth', ' this sentence is long.']

s2 = "Shorter String"

down_s2 = string2.lower()       # down_s2 ='shorter string'
up_s2 = string2.upper()         # up_s2 = 'SHORTER STRING'

up_s2.isalpha()                 # True
up_s2.islower()                 # False
down_s2.islower()               # True
s2.isspace()                    # False
" ".isspace()                   # True
{% endhighlight %} 
</p>

<p>
Source code, including its strings and identifiers, is parsed in 
<a href="https://docs.python.org/3/howto/unicode.html" target="_blank">UTF-8</a>
by default. Strings are 
<a href="https://www.python.org/dev/peps/pep-0393/" target="_blank">internally
represented</a>
in bare Unicode. Strings
containing only ASCII or Latin-1 characters use 1 byte for all characters. Strings
containing any higher code point characters use 2 (UCS-2) or 4 (UCS-4) bytes for all characters,
depending on the value of the highest code point. Base size of strings vary
dependent on the internal representation. 

{% highlight python %}
# Precise size may vary based on interpreter version
s1 = ""         # 49 bytes 
s1 = "aa"       # 51 bytes, 1 per char

# Latin-1 containing string has larger base size
s2 = "À"        # 74 bytes
s2 = "Àa"       # 75 bytes, 1 per char

# String containing code point >255
s3 = "ƻ"        # 76 bytes
s3 = "ƻa"       # 78 bytes, 2 per char (UCS-2)
{% endhighlight %}
</p>


<p>
Short strings may be dynamically 
<a
href="https://www.codementor.io/satwikkansal/do-you-really-think-you-know-strings-in-python-fnxh8mtha"
target="_blank">interned</a>, where a singular string object is referenced for
variables assigned to the same string literal. 
<a
href="https://www.codementor.io/mjpieters/python-optimization-how-it-can-make-you-a-better-programmer-ajiiftqbo"
target="_blank">Constants</a>
may be created for strings and other data types
during bytecode generation. It is not possible to explicitly declare a variable
as constant. 
</p>

<div class="pagination">

    <a class="pagination-item" href="{{ site.baseurl }}
    {% link _posts/Python-Guide/2018-06-14-getting-start-python.md %}">Previous</a>

    <a class="pagination-item" href="{{ site.baseurl }}
    {% link _posts/Python-Guide/2018-06-14-python-as-second-language.md %}">Guide</a>

    <a class="pagination-item" href="{{ site.baseurl }}
    {% link _posts/Python-Guide/2018-06-14-data-structures-python.md %}">Next</a>

</div>

