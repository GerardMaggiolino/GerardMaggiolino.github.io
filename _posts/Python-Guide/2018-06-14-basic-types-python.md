---
layout: post
title: "Python: Basic Types, Syntax, and Operations"
categories: programming learning python
---
<p class="message">
    Page under development. 
</p>

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
my_var = 5                  # Assigning an integer to my_var
my_var = "Five"             # Reassigning my_var to a string

other_var = 10 
print(my_var + other_var)   # Error thrown! Unrelated types {% endhighlight %}
</p>

<p>
The related types of integers and floating point numbers may be operated on with
standard arithmetic operators. There are no distinctions between longs and ints,
and ints are 
<a
href="https://www.geeksforgeeks.org/what-is-maximum-possible-value-of-an-integer-in-python/"
target="_blank">unbounded</a> in maximum value, restricted only by available memory.
{% highlight python %}
x = 3.0                     # Assigning a floating point
y = 10                      # Assigning an integer

z = x + y                   # Addition, z = 13.0
z = x - y                   # Subtraction, z = -7.0 
z = x * y                   # Multiplication, z = 30.0
z = y % 3                   # Modulus, z = 1

z = y / 3                   # Floating point division, z = 
                            #   3.33333333 ... 
z = y // 3                  # Truncated division, z = 3
z = y // 3.0                # Truncated division, z = 3.0
z = y ** x                  # Exponentiation, z = 1000.0{% endhighlight %}
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
x = int(my_bool)            # x = 1

my_bool = False
y = float(my_bool)          # y = 0.0

x = 100
my_bool = bool(x)           # my_bool = True
my_bool = bool(y)           # my_bool = False{% endhighlight %}
</p>

<p>
Singular types of byte, char, short, and long are unified under integer types. Float
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
type(bar)                   # <class 'int'>

bar = 5.
type(bar)                   # <class 'float'>

bar = True
type(bar)                   # <class 'bool'>

bar = None
type(bar)                   # <class 'NoneType'>{% endhighlight %}
</p>

<p>
The built in function 
<a href="https://docs.python.org/3/library/functions.html#id" target="_blank">
id()</a> returns the memory address of an object (for CPython). This can be used
to demonstrate immutability and referencing. The covered types of
bool, int, and float are immutable, and reassignment of variable names create
new objects. Try the following on your terminal; memory addresses will vary.
{% highlight python %}
foo = 5                     # new int object created
id(foo)                     # 4372930720 

foo = 10                    # new int object created
id(foo)                     # 4372930880

foo = True                  # new bool object created
id(foo)                     # 4372526608{% endhighlight %}


The above comments of object creation are not precisely true - integers in the
range of [-5, 256] are cached, along with bool objects. The variable name
of foo can be thought to be reassigned to existing objects. 
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
hex(id(foo))                # 0x1049a0140
hex(id(bar))                # 0x1049a0140

# foo refers to newly created int object
foo = 300
hex(id(foo))                # 0x104c16f70{% endhighlight %}

These optimizations are not guaranteed, particularly for larger integers and complex objects.
As expected, all objects are placed on a 
<a href="https://docs.python.org/3/c-api/memory.html" target="_blank">private heap</a>,
and garbage collection of unreferenced objects is automatic. Size of
objects may vary based on implementation, but integers are often at least 28
bytes, far larger than most other language's 4 or 8 bytes. This reflects that
they are complete objects with many attributes. 
</p>

<div class="pagination">

    <a class="pagination-item" href="{{ site.baseurl }}
    {% link _posts/Python-Guide/2018-06-14-getting-start-python.md %}">Previous Article</a>

    <a class="pagination-item" href="{{ site.baseurl }}
    {% link _posts/Python-Guide/2018-06-14-python-as-second-language.md %}">Guide</a>

    <span class="pagination-item">Next Article</span>

</div>

