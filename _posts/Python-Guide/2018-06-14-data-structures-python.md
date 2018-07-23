---
layout: post
title: "Python: Data Structures" 
categories: programming learning python
---

<p class="message">Page under development.</p>
<div class="section" id="immutable">Immutable Data Structures</div>

<p>
Covered types of bool, string, int, and float are immutable, as are the built in
data structures of tuple and frozenset. Generics or template based data
structures are not available. Structures cannot be bound to single types. 
</p>


<p>
Tuples are declared with '()'. Non-empty tuples can be declared without
parenthesis, with commas separating elements; this is called 
<a href="http://www.schoolcoders.com/coding-pythonbeginners-tuples-2"
target="_blank">packing</a>. 
Single element tuples must have a
comma after the element. Tuple elements are accessible with
indexing. Slicing returns new tuples. 
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
t1[:]        # ('Gary', 'Rick', 5)
{% endhighlight %}
</p>


<p>
Tuples are concatenated with '+'. The "in"
operator is used to check for membership of an element, returning bool.
Tuple has two
<a href="https://www.programiz.com/python-programming/methods/tuple"
target="_blank">methods</a> and many callable functions.
Function len() returns the number of elements, and 
<a href="https://docs.python.org/3/library/functions.html#sorted"
target="_blank">sorted()</a> returns a new sorted list; list is a mutable data
structure. Operating on a passed element, method index()
returns the index of the first occurrence and count() returns the total occurrences.
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
mutate the frozenset. Sets will be covered in the next section. 
</p>


<div class="section" id="mutable">Mutable Data Structures</div>
<p>

</p>


<div class="pagination">

    <a class="pagination-item" href="{{ site.baseurl }}
    {% link _posts/Python-Guide/2018-06-14-basic-types-python.md %}">Previous</a>

    <a class="pagination-item" href="{{ site.baseurl }}
    {% link _posts/Python-Guide/2018-06-14-python-as-second-language.md %}">Guide</a>

    <span class="pagination-item">Next</span>

</div>

