---
layout: post
title: "Python: Basic Types and Operations"
categories: programming learning python
---
<p class="message">
    Page under development. 
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
names may be reassigned to other objects; types are bound to values rather than
to variable names (dynamic typing). However, operations on unrelated
types aren't permitted without explicit casting (strong typing). 
{% highlight python %}
# Comments are designated by a hash 
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
between two integers to return an integer. 
</p>

<p>
Floating points, integers, and booleans may be converted between one
another with type conversion functions. Booleans are assigned values of
upper-case True or False. 
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
The built in function of 
<a href="https://docs.python.org/3/library/functions.html#type" target="_blank">
type()</a>
may be used to return the type of an object. The function 
<a href="https://docs.python.org/3/library/functions.html#id" target="_blank">
id()</a> returns the memory address of an object (for CPython). This can be used
to demonstrate immutability and referencing of primitives. 
</p>

<div class="pagination">

    <a class="pagination-item older" href="{{ site.baseurl }}
    {% link _posts/Python-Guide/2018-06-14-getting-start-python.md %}">Previous Article</a>

    <a class="pagination-item" href="{{ site.baseurl }}
    {% link _posts/Python-Guide/2018-06-14-python-as-second-language.md %}">Guide</a>

    <span class="pagination-item newer">Next Article</span>

</div>

