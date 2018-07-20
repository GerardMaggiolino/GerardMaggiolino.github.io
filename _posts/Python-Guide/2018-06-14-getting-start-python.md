---
layout: post
title: "Python: Getting Started"
categories: programming learning python
---

<p class="message">
    Under development. This post will contain information to make sure you're
    set up to start programming in Python!
</p>

<p>
    This guide is designed for programmers with prior language knowledge to rapidly
develop skills in Python. Early articles are meant to port over existing 
knowledge into Python syntax, without programming exercises. Deeper specifications of
the language will be covered along the way, with links to resources covering
material outside of the scope of this tutorial. 
</p>

<p>
This 
    <a href="https://www.youtube.com/watch?v=YYXdXT2l-Gg" target="_blank">video</a>
will provide a thorough review for installation on Mac and Windows, although
alternative resources can be found through a google search.
These articles will assume Python 3.x is being used on a Unix-like environment.
Running either of 
  {% highlight bash %}
python --version
python3 --version{% endhighlight %} 
on the command line should display the version number of each
interpreter. Recent releases can be installed directly from 
    <a href="https://www.python.org/downloads/" target="_blank">the Python website.</a>
<p>

<p>
Python is an interpreted
language. In essence, written source code is ran on a
secondary program which executes the instructions. The most common interpreter,
CPython, is written in C; this virtual machine will execute Python 
<a href="https://opensource.com/article/18/4/introduction-python-bytecode"
target="_blank">bytecode</a>
which is generated prior to runtime from source code. From the users end, this
is a one step process. Invoking the Python interpreter will allow the same
source code to run platform independently. These tutorials will assume Python is
being ran from the command line, although many powerful
<a href="https://realpython.com/python-ides-code-editors-guide/" target="_blank">
IDEs</a>
compatible with or designed for Python exist. 
</p>

<p>
Python files are designated by .py extensions. General style guidelines are
found in 
<a href="https://www.python.org/dev/peps/pep-0008/" target="_blank">PEP8</a>. Of
note is the preferred indentation method of spaces. Python uses whitespace to
structure code blocks rather than braces, and mixed tabs and spaces will throw 
errors. 
</p>

<p>
Simply running "python" from the command line will open an interactive 
shell-like environment reading from standard input. Specifying a file name will
sequentially execute a script from that file. Appending the following to the top
of a script
  {% highlight python %}
"#!/usr/local/bin/python3"
  {% endhighlight %}
with substitution of the correct path to the interpreter of choice allows for
the script to be ran directly when given 
<a href="https://www.computerhope.com/unix/uchmod.htm" target="_blank">execution</a>
permissions. 
</p>
<div class="pagination">

    <span class="pagination-item older">Previous Article</span>

    <a class="pagination-item" href="{{ site.baseurl }}
    {% link _posts/Python-Guide/2018-06-14-python-as-second-language.md %}">Guide</a>

    <span class="pagination-item newer">Next Article</span>

</div>

