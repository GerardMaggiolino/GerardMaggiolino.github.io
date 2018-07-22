---
layout: post
title: "Python: Getting Started"
categories: programming learning python
---
<p>
    This guide is designed for programmers with prior language knowledge to rapidly
develop skills in Python. Early articles are meant to port over existing 
knowledge into Python syntax, without programming exercises. Deeper specifications 
of the language will be covered along the way, with links to additional 
resources covering material outside of the scope of this tutorial. Familiarity 
with C, C++, Java, or similar languages is expected.
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
language. Written source code is run on a
secondary program which executes the instructions. The most common, reference
interpreter is
<a href="https://docs.python-guide.org/starting/which-python/#implementations"
target="_blank">CPython</a>. This virtual machine will execute Python 
<a href="https://opensource.com/article/18/4/introduction-python-bytecode"
target="_blank">bytecode</a>, generated prior to runtime from source code. From the users end, this
is a one step process. Invoking the Python interpreter will allow the same
source code to run platform independently. These tutorials will assume Python is
being run from the command line, although many powerful
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
of a file
  {% highlight python %}
#!/usr/local/bin/python3{% endhighlight %}
with substitution of the correct path to the interpreter of choice allows for
the script to be run directly when given 
<a href="https://www.computerhope.com/unix/uchmod.htm" target="_blank">execution</a>
permissions. 
</p>

<p>
Ensure that you've installed and are able to run Python
scripts. First, run Python from the command line (it may be helpful to 
<a href="https://jonsuh.com/blog/bash-command-line-shortcuts/"
target="_blank">alias</a>
python3 to python).
{% highlight bash %}
python
>>> print("Hello, World!")
Hello World!
>>> Ctrl-D{% endhighlight %}
Then, create a file "HelloWorld.py", specifying the correct path to your
interpreter. 
{% highlight python %}
#!/usr/local/bin/python3#!/usr/local/bin/python3#!/usr/local/bin/python3
print("Hello World!"){% endhighlight %}
You can run the file from the command line using either 
{% highlight bash %}
python HelloWorld.py{% endhighlight %}
or by setting execution permissions for the file and running it directly. 
{% highlight bash %}
chmod a+x HelloWorld.py
./HelloWorld.py{% endhighlight %}
</p>

<p>
Now that you're able to run Python code and have an abstract sense of the
language, it's time to start learning! Keep in mind that concepts which have not
yet been formally covered may be used to demonstrate other features of Python. Do
your best to infer its use for the time being; for example, the print() function
will print text to standard output. Any code shown will execute
properly unless otherwise noted.  
</p>
<div class="pagination">

    <span class="pagination-item older">Previous</span>

    <a class="pagination-item" href="{{ site.baseurl }}
    {% link _posts/Python-Guide/2018-06-14-python-as-second-language.md %}">Guide</a>

    <a class="pagination-item newer" href="{{ site.baseurl }}
    {% link _posts/Python-Guide/2018-06-14-basic-types-python.md %}">Next
    </a>


</div>

