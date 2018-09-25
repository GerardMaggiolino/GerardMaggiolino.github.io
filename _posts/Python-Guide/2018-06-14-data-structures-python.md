---
layout: post
title: "Python: Data Structures" 
categories: programming learning python
---

<div class="section" id="Tuples">Tuples</div>

<p>
Covered types of bool, string, int, and float are immutable, as are the built in
data structures of tuple and frozenset. Generics or template based data
structures are not available. Structures cannot be bound to single types. The
function 
<a href="https://docs.python.org/3/library/functions.html#len"
target="_blank">len(<i>object</i>)</a> can be used uniformly on all mutable and immutable data
structures to return the number of elements. 
</p>


<p>
Tuples are ordered collections of objects declared with '()'. Non-empty tuples can be declared without
parenthesis, with commas separating elements; this is called 
<a href="http://www.schoolcoders.com/coding-pythonbeginners-tuples-2"
target="_blank">packing</a>. 
Single element tuples must have a
comma after the element. Tuple elements are accessible with
indexing. Slicing returns new tuples, as does *, which repeats a tuple
with functionality similar to strings.
{% highlight python %}
empty_tuple = ()

singleton = (5,)
singleton = 5,

t1 = ("Gary", "Rick", 5)
t1 = "Gary", "Rick", 5

t1[0]       # 'Gary'
t1[-1]      # 5
t1[0:2]     # ('Gary', 'Rick')
t1[0:1]     # ('Gary',)     

# Creates shallow copy of tuple 
t1[:]       # ('Gary', 'Rick', 5)

t1[:2] * 2  # ('Gary', 'Rick', 'Gary', 'Rick')
{% endhighlight %}
</p>


<p>
Tuples are concatenated with '+'. The 'in'
operator is used to check for membership of an element, returning bool.
Tuple has two
<a href="https://www.programiz.com/python-programming/methods/tuple"
target="_blank">methods</a> and many callable functions. Function
<a href="https://docs.python.org/3/library/functions.html#sorted"
target="_blank">sorted(<i>object</i>)</a> returns a new sorted list; list is a mutable data
structure. Operating on a passed element, method index(<i>object</i>)
returns the index of the first occurrence and count(<i>object</i>) returns the total occurrences.
{% highlight python %}
t2 = 5, 3, 5, 4

t3 = t2[0:1] + t2[:]
# t3 = (5, 5, 3, 5, 4)

4 in t3         # True 
0 in t3         # False
len(t3)         # 5

sorted_list = sorted(t3)
# sorted_list = [3, 4, 5, 5, 5]

t3.index(5)     # 0
t3.index(3)     # 2
t3.count(5)     # 3
t3.count(1)     # 0

len(t3)         # 5
{% endhighlight %}

Multiple variables can be assigned from elements of a tuple with unpacking, the
reverse of packing, done above. Parenthesis can be omitted on either side of the
assignment. 
{% highlight python %}

packed_tup = 1, 2, 'Sally'

num1, num2, name = packed_tup

num1                    # 1
num2                    # 2
name                    # 'Sally'

num_tup = num1, num2    # num_tup = (1, 2)

# This is useful for swapping variables without a tmp!
num1, num2 = num2, num1

num1                    # 2
num2                    # 1 
{% endhighlight %}

Frozenset is identical to set, but restricted to methods which do not
mutate the structure. Sets will be covered in the next section. 
</p>


<div class="section" id="list">Lists</div>

<p>
Lists are mutable ordered collections of objects declared with '[]'. There is similar
functionality with indexing, slicing, '*', '+', 'in', 
<a href="https://docs.python.org/3/library/functions.html#sorted"
target="_blank">sorted(<i>object</i>)</a>, index(<i>object</i>), and count(<i>object</i>). You may notice strings,
tuples, and lists are handled similarly. These structures are all 
<a href="https://docs.python.org/3/library/stdtypes.html#typeiter"
target="_blank">iterable</a>
sequences, a concept which will be covered later; in essence, iterables can be
iterated over to obtain subobjects.  
{% highlight python %}l1 = ['cat', 'dog']

l2 = l1 + l1
# l2 = ['cat', 'dog', 'cat', 'dog']

l2 = l2[0:3]
# l2 = ['cat', 'dog', 'cat']

l2.index("dog")     # 1
l2.index("cat")     # 0
l2.count("cat")     # 2

len(l2)             # 3

l3 = sorted(l2)
# l3 = ['cat', 'cat', 'dog']
{% endhighlight %}
</p>

<p>
Mutability of lists allows for elements to be inserted, removed, and
reorganized with a variety of 
<a href="https://www.programiz.com/python-programming/methods/list"
target="_blank">methods</a>. Method append(<i>object</i>) attaches a single element,
extend(<i>object</i>) merges elements of another iterable, and
insert(<i>index</i>, <i>object</i>) inserts at a specified index. Individual
indices can be reassigned with standard indexing. 
{% highlight python %}
l1 = ['fish']

l1.append(5)
l1                  # ['fish', 5]

sublist = ['cat', 'dog']
l1.append(sublist)  
l1                  # ['fish', 5, ['cat', 'dog']]

tup = ('fu', 'baz')
l2 = ['foo', 'bar']
l2.extend(tup)
l2                  # ['foo', 'bar', 'fu', 'baz']

l2.insert(1, 'new')
l2                  #['foo', 'new', 'bar', 'fu', 'baz']

l2[0] = 'newnew'
l2                  #['newnew', 'new', 'bar', 'fu', 'baz']
{% endhighlight %}
</p>

<p>
Method remove(<i>object</i>) removes the first matching object,
pop(<i>index</i>) removes and returns the object at an index, and statement 
<a href="https://docs.python.org/3/reference/simple_stmts.html#del"
target="_blank">del</a> can be used to remove single or multiple elements with
splicing and indexing. 
{% highlight python %} 
l1 = ['a', 'b', 'c']

letter = l1.pop(0)  
# letter = 'a'

l1              # ['b', 'c']

l1.remove('c')
l1              # ['b']

l1.extend(['c', 'd', 'e'])
del l1[0:3]
l1              # ['e']
del l1[0]       
l1              # []
{% endhighlight %}

</p>

<p>
Method copy() returns a shallow copy of the list, similar to slicing with no
start or end specified. Similar to references or pointers in other languages,
assignment to a new variable name does not create new objects implicitly, and
both variables will now refer to the same object on the private heap; thus,
changes in one will be reflected in the other. 
{% highlight python %}l1 = ['a', 'b', 'c']

# Two variables referencing same object
l2 = l1
del l1[0]
l2          # ['b', 'c']

l3 = [1, 2, 3, 4]
# Both create shallow copies 
l4 = l3.copy()
l4 = l3[:]

# Shallow copy created two, distinct identical list objects
del l3[0:2]
l4          # [1, 2, 3, 4]
{% endhighlight %}
</p>

<p>
Mutability requires a more nuanced understanding of referencing. Tuples and
lists store references to objects at indices, rather than the objects themselves.
Thus, changing the object which a reference at an index points to changes the
outer list as well. This is best demonstrated. 
{% highlight python %}l1 = ['a', 'b']
l2 = ['c', 'd']
outer = l1, l2
# outer = (['a', 'b'], ['c', 'd'])

l1[0] = 'z'
outer           # (['z', 'b'], ['c', 'd'])

l1[1] = 'z'
outer           # (['z', 'z'], ['c', 'd'])    
{% endhighlight %}

General implications of shallow copies hold. 
{% highlight python %}l1 = [1, 2, 3]
outer = [l1, 4, 5]
outer                   # [[1, 2, 3], 4, 5]

clist = outer.copy()

del outer[1:]
outer                   # [[1, 2, 3]]

l1[0] = 100

outer                   # [[100, 2, 3]]
clist                   # [[100, 2, 3], 4, 5]
{% endhighlight %} 
However, '==' may be used to test deep equality of built-in types. 
{% highlight python %}
list1 = [1, 2, 3] 
list2 = [1, 2, 3] 
tuple1 = 1, 2, 3, list1
tuple2 = 1, 2, 3, list2
dict1 = {'first': tuple1}
dict2 = {'first': tuple2}
   
# All objects at different memory locations
id(list1) == id(list2)      # False
id(tuple1) == id(tuple2)    # False
id(dict2) == id(dict2)      # False

dict1 == dict2              # True
{% endhighlight %}
</p>



<div class="section" id="dictionary">Dictionaries</div>

<p>
Dictionaries are mutable iterable 
<a href="https://docs.python.org/3/library/stdtypes.html#typesmapping"
target="_blank">mappings</a> of immutable hashable keys to arbitrary objects,
declared with {}, best described as a hash table. The 
<a href="https://docs.python.org/3/library/stdtypes.html#dict" target="_blank">
dict()</a> constructor can
be used to more rapidly and cleanly declare dictionaries with iterables and the
<a href="https://docs.python.org/3/library/functions.html#zip"
target="_blank">zip(<i>*iterables</i>)</a> function (note: the * signifies
variable number of arguments accepted). This returns an iterable zip object where each
tuple at an index is constructed with each passed iterable's element of the
same index. A dictionary may take any iterable where elements are iterables
of two objects; zip aids with constructing such an iterable. 
{% highlight python %}
# Standard assignment with key: value syntax
dict1 = {'one': 1, 'two': 2, 'three': 3}

# Using dict() constructor 
dict2 = dict([('one', 1), ('two', 2), ('three', 3)])

# Using zip
iter1 = ['one', 'two', 'three']
iter2 = (1, 2, 3)
dict3 = dict(zip(iter1, iter2))

dict1 == dict2 == dict3     # True

# More on zip 
iter3 = 'abc'
zipObj = zip(iter1, iter2, iter3)

next(zipObj)                # ('one', 1, 'a')
next(zipObj)                # ('two', 2, 'b')
{% endhighlight %}
</p>

<p>
Values at a key can be set or reassigned using indexing with []. Retrieval of
elements with [] raises a KeyError exception (more on exceptions later) if the
key is not present in the dictionary. Using method get(<i>key</i>) returns the
associated value or a default value of None if the key is not present; a second 
argument may be used to set the default value. 
{% highlight python %}
grade_book = {'Bob': 'A', 'Sue': 'B', 'Joe': 'C', 'Fred': 'D'}

# Retrieval with brackets
grade_book['Bob']           # 'A'
grade_book['Gary']          # KeyError exception thrown! 

# Retrieval with get()
grade_book.get('Joe')       # 'C'
grade_book.get('Gary')      # None
grade_book.get('Gary', 0)   # 0 

# Adding new key value pair, reassigning key
grade_book['New Guy'] = 'A'
grade_book['Bob'] = 'C'

grade_book
# {'Bob': 'C', 'Sue': 'B', 'Joe': 'C', 'Fred': 'D', 'New Guy': 'A'}
{% endhighlight %}

Dictionaries can be combined with the update(<i>dict</i>) method. Duplicate keys
from the passed dictionary will replace the key values from the calling
dictionary. 

{% highlight python %}
friends_ages = {'Bob': 18, 'Fred': 20}
new_friends = {'John': 31, 'Fred': 15}

friends_ages.update(new_friends)
friends_ages
# {'Bob': 18, 'Fred': 15, 'John': 31} 
{% endhighlight %}

Items can be deleted with the del statement, specifying the key. The in operator
is used to check for item membership, again by key. 
{% highlight python %}
prices = {"Cheese": 12, "Steak": 15, "Wine": 31}

'Cheese' in prices      # True
del prices['Cheese']    
'Cheese' in prices      # False
{% endhighlight %}
Keys, values, and key-value pairs (items) can obtained as an iterable view
object. 

</p>

<div class="pagination">

    <a class="pagination-item" href="{{ site.baseurl }}
    {% link _posts/Python-Guide/2018-06-14-basic-types-python.md %}">Previous</a>

    <a class="pagination-item" href="{{ site.baseurl }}
    {% link _posts/Python-Guide/2018-06-14-python-as-second-language.md %}">Guide</a>

    <span class="pagination-item">Next</span>

</div>


