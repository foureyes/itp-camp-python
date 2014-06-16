---
layout: slides
title: Functions 
---
<section markdown="block" class="title-slide">
# Functions 
{% include title-slide-footer.html %}
</section>

<section markdown="block">
## A Quick Review
</section>

<section markdown="block">
### Functions...

__What's a function?__

<div class="incremental" markdown="block">
A __function__ is a named sequence of statements that performs some _useful_ operation
</div>
</section>

<section markdown="block">
### Method Definition

__What's a method (well... in the context of programming, of course!)?__

<div class="incremental" markdown="block">
A __method__ is an action that an object/_thing_ can do.  It's basically a function that's attached to an object. 
</div>
</section>

<section markdown="block">
### Function Call Definition

__What's a function call?__ 

<div class="incremental" markdown="block">
A __function call__ is the statement that actually executes a function.  It's just the function's name followed by parentheses, with zero or more arguments within those parentheses.
</div>
</section>

<section markdown="block">
### Argument Definition

__What's an argument (again, in the context of functions, of course)?__ 

<div class="incremental" markdown="block">
An __argument__ is a value that's passed in to a function when a function is called.  It's the input!
</div>
</section>



<section markdown="block">
## Defining Functions
</section>

<section markdown="block">
### Our Very Own Functions!

* we can actually create our own functions
* that means:
	* we can group a bunch of statements together
	* name that group of statements
	* __execute that group of statements simply by calling its name!__
</section>

<section markdown="block">
### Motivation for Creating Functions

__Why would the ability to create our own functions be useful?__ &rarr;

<div class="incremental" markdown="block">
* reduce repetitive code (instead of typing in the group of statements multiple times, just call function)
* break down programming problem into discrete tasks
	* complexity of each sub-task or function is more manageable than dealing with program in its entirity
	* easier to test each individual function or component 
* create your own tools for solving a problem
	* it's almost like defining your own __problem domain__ specific language
</div>
</section>


<section markdown="block">
### Defining a Function Continued

1. a function definition always starts with the __reserved__ word, __def__ (__the function header__)
2. ... followed by the name of your function
	* (function names adhere to the same rules as variable names)
3. ... followed by parentheses
4. with an __optional__, comma separated list of inputs enclosed in parentheses (depends on function)
	* if the __parentheses are empty (), then the function is being called without arguments__
	* __end with a colon__
5. lastly, an indented block of code (__the function body__)
	* this is just one level of indentation in &rarr;
</section>

<section markdown="block">
### What's This About an Indented Block?

* remember - in Python, __whitespace characters__ (such as space, tabs, newlines, etc.) are __significant__
* __consecutive lines of code__ can be grouped together based on __indentation__
* you can tell the start and end of a function body by its level of indentation
* it is indented one level in from the function header
</section>

<section markdown="block">
### An Indented Block for the Function Body

{% highlight python %}
def the_name_of_your_function(parameter_1, paramter_2):
	# inside the function
	print("something")
	print("another thing")

# outside of the function
print("and another thing")
{% endhighlight %}
</section>

<section markdown="block">
### Let's Try Creating a Function!

__Write a function called say_multilingual_meow:__ &rarr;

* it'll [say meow in two different languages](http://www.eleceng.adelaide.edu.au/personal/dabbott/animal.html)
* it should print out two lines
* one line with "meow", the other line with "nyan"
* use variables to represent the two types of meow ...

<div class="incremental" markdown="block">
{% highlight python %}
def say_multilingual_meow():
	japanese_meow = "nyan"
	english_meow = "meow"
	print(japanese_meow)
	print(english_meow)
{% endhighlight %}
</div>
</section>

<section markdown="block">
### Some Terminology


__function definition__ - all of the code for a function

__function header__ - the beginning of the function: its name and optional list of parameters

__function body__ - the code that gets executed when a function is called..

__What is the defintion, header and body of the function we defined below?__ &rarr;

{% highlight python %}
def say_multilingual_meow():
	japanese_meow = "nyan"
	english_meow = "meow"
	print(japanese_meow)
	print(english_meow)
{% endhighlight %}
</section>

<section markdown="block">
### Calling Your Function

So... now that you have a shiny new function, __how would you call it?__ &rarr;

{% highlight python %}
def say_multilingual_meow():
	japanese_meow = "nyan"
	english_meow = "meow"
	print(japanese_meow)
	print(english_meow)
{% endhighlight %}

<div class="incremental" markdown="block">
{% highlight python %}
"""
Once the function is defined in your file, you can call it!
"""

say_multilingual_meow()
{% endhighlight %}
</div>
</section>


<section markdown="block">
### Let's See How This All Works!

In one file, write the function definition and function call from the previous slides.  

* try running it!  
* print out "done" after your function call
* __what do you think the output will be?__ &rarr;

{% highlight python %}
def say_multilingual_meow():
	japanese_meow = "nyan"
	english_meow = "meow"
	print(japanese_meow)
	print(english_meow)

say_multilingual_meow()
print("done!")
{% endhighlight %}

<div class="incremental" markdown="block">
{% highlight python %}
nyan
meow
done!
{% endhighlight %}
</div>
</section>

<section markdown="block">
### Calling Your Function Continued

So... [what actually happened there](http://www.pythontutor.com/visualize.html#code=def+say_multilingual_meow()%3A%0A%09japanese_meow+%3D+%22nyan%22%0A%09english_meow+%3D+%22meow%22%0A%09print(japanese_meow)%0A%09print(english_meow)%0A%0Asay_multilingual_meow()%0Aprint(%22done!%22)&mode=display&cumulative=false&heapPrimitives=false&drawParentPointers=false&textReferences=false&showOnlyOutputs=false&py=3&curInstr=0)? &rarr;

{% highlight python %}
def say_multilingual_meow():
	japanese_meow = "nyan"
	english_meow = "meow"
	print(japanese_meow)
	print(english_meow)

say_multilingual_meow()
print("done!")
{% endhighlight %}

* when you call your function...
* imagine that you're jumping back to your function definition
* ...and then executing the body of your function
* once it's done, execution goes back to where you called your function (printed done for clarity)
</section>

<section markdown="block">
### Before and After the Function Call

__What does this program output?__ &rarr;

{% highlight python %}
def say_multilingual_meow():
	japanese_meow = "nyan"
	english_meow = "meow"
	print(japanese_meow)
	print(english_meow)

print('cat sounds:') 
say_multilingual_meow()
print('dog sounds:')
print('woof')
{% endhighlight %}

</section>

<section markdown="block">
### Before and After the Function Call... Output

{% highlight python %}
cat sounds:
nyan
meow
dog sounds:
woof
{% endhighlight %}
</section>

<section markdown="block">
### Just the Definitions, Please!

Let's look at the same program, but without the function __call__.  __What do you think the output of this program will be if the function definition is the only code present in your program?__ &rarr;
{% highlight python %}
def say_multilingual_meow():
	japanese_meow = "nyan"
	english_meow = "meow"
	print(japanese_meow)
	print(english_meow)
{% endhighlight %}

<div class="incremental" markdown="block">
{% highlight python %}
 
{% endhighlight %}

(That's supposed to be nothing!  A function definition alone won't execute the code in a function.)
</div>
</section>

<section markdown="block">
### Just the Calls, Please!

What about this version of the program (again, this is the only code in the program)? __What do you think the output will be?__ &rarr;

{% highlight python %}
say_multilingual_meow()
{% endhighlight %}

<div class="incremental" markdown="block">
We get a NameError!

{% highlight python %}
Traceback (most recent call last):
  File "/tmp/foo.py", line 1, in <module>
    say_multilingual_meow()
NameError: name 'say_multilingual_meow' is not defined
{% endhighlight %}

__A function has to be defined before it can be used.__
</div>
</section>

<section markdown="block">
### Multiple Function Definitions

You can define more than one function in your program!

{% highlight python %}
def my_first_function():
	print("first")

def my_second_function():
	print("second")
{% endhighlight %}
</section>

<section markdown="block">
### Functions in Functions

In fact, you can use a function that you've already defined in another function that you're creating.  __What do you think the output of this program will be?__ &rarr;

{% highlight python %}
def say_moo():
	print("moo")

def main():
	say_moo()
	say_moo()

main()
{% endhighlight %}

<div class="incremental" markdown="block">
{% highlight python %}
moo
moo
{% endhighlight %}
</div>
</section>

<section markdown="block">
### Functions in Functions Continued

Notice that in the previous code...

{% highlight python %}
def say_moo():
	print("moo")

def main():
	say_moo()
	say_moo()

main()
{% endhighlight %}

* we defined a function called __say_moo__
* we defined another function called __main__ that uses __say_moo__
</section>

<section markdown="block">
### "Local" Variables

* a __local__ variable is a variable created inside a function's definition
* another way of saying this is: all of the variables in your function definition are __local__ to that function
* they cannot be used / accessed by statements outside of the current function definition
* different functions can have local variables of the same name, and they will not interfere with each other
* __scope__ is the part of the program where a variable can be accessed
* a __local__ variable's scope is the function in which it was defined

</section>

<section markdown="block">
### "Local" Variables Continued


{% highlight python %}
def my_first_function():
	a = 1
	print(a)

def my_second_function():
	b = 2
	print(b)
{% endhighlight %}

The variables __a__ and __b__ are __local__ to __my\_first\_function__ and __my\_second\_function__ respectively.

__a__ is within the __scope__ of my\_first\_function and __b__ is within the __scope__ of my\_second\_function.

</section>

<section markdown="block">
### "Local" Variables Continued Some More

In fact... because variables defined within a function are local, using the variable name in two different functions doesn't cause any errors, and nothing gets overwritten. __What will this program output?__ &rarr;

{% highlight python %}
def my_first_function():
	a = 1
	print(a)

def my_second_function():
	a = 200
	print(a)

my_first_function()
my_second_function()
my_first_function()
{% endhighlight %}
<div class="incremental" markdown="block">
1, 200, and then 1 again
</div>
</section>


<section markdown="block">
### Scope Summary

* variables declared outside of a function can be accessed within a function
* variables declared inside of a function cannot be accessed outside of a function (they're __out of scope__)
* parameters in a function cannot be accessed outside of a function either
* variables declared within a function don't override those declared outside of a function
</section>




<section markdown="block">
## Fruitful Functions
</section>

<section markdown="block">
### Functions That Return Values

We've used some functions that return values, and we looked at them in an earlier set of slides.  __What type of values do the following functions give back? &rarr;__

* randint(1, 10)
* input("Enter a number")
* float(23)

<div class="incremental" markdown="block">
* int
* str
* float
</div>
</section>

<section markdown="block">
### What About the Functions We've Been Writing

If you assigned the result of one of the functions that we defined, what would get back? __What gets printed to the screen in the following program... and why? &rarr;__

{% highlight python %}
def say_multilingual_meow():
	japanese_meow = "nyan"
	english_meow = "meow"
	print(japanese_meow)
	print(english_meow)
{% endhighlight %}
</section>

<section markdown="block">
### The Functions That We Wrote Don't Return Anything!

The result from the previous slide would be:

{% highlight python %}
hellohellohellohellohello
None
{% endhighlight %}

* hellohellohellohellohello comes from the print in the function
* but __None__ comes from the result of calling the function!
* it doesn't return anything, so we get None back
</section>
<section markdown="block">
### Return Continued

__If a function doesn't return anything...__

it gives back

__None__ 
</section>

<section markdown="block">
### None 

Before we go on.  Let's talk about _nothing_.

... or rather ...

__None__ is a special value in Python that represents the absence of a value. Let's try it out.  &rarr;
</section>

<section markdown="block">
### Returning Values

* we can create _fruitful_ functions, that is... functions that return a value
* just use the keyword __return__, followed by the value that you want to give back
* here's an example of a function that gives back a value

{% highlight python %}
def greet(greeting, num):
	s = greeting * num
	return s
{% endhighlight %}
</section>

<section markdown="block">
### So, Now What?

Now that you have a function that returns a value, you can use that function wherever you would use that value.

{% highlight python %}
def greet(greeting, num):
	s = greeting * num
	return s

# using the return value of greet as an argument to input!
response = raw_input(greet("hi", 3))
print(response)
{% endhighlight %}
</section>

<section markdown="block">
### The return Statement

* the __return__ immediately stops the execution of a function
* ...and returns the value that follows it
	* the value can be any value!
	* it can even be an expression
</section>

<section markdown="block">
### Some Examples of the Return Statement

These functions are contrived examples of what you can do with return.  __What type and value do they return? &rarr;__

{% highlight python %}
def foo():
	return "foo"

def bar():
	return "b" + "ar"

def baz():
	return str(math.sqrt(100)) + "!"
{% endhighlight %}

<div class="incremental" markdown="block">
* string, "foo"
* string, "bar"
* string, "10!"
</div>
</section>

<section markdown="block">
### Let's Try Creating a Function That Returns a Value

__Write a function that returns the area of a circle (&pi;r&sup2;)when given a radius, r.&rarr;__

<div class="incremental" markdown="block">
{% highlight python %}
import math
def area(r):
	a = math.pi * r * r
	return a
{% endhighlight %}
</div>
</section>

<section markdown="block">
### Area, Defined Again

Another way to define our area function:

{% highlight python %}
import math
def area(r):
	return  math.pi * r * r
{% endhighlight %}

* code is shorter 
* but no intermediary variable (maybe more difficult to debug?) 
</section>

<section markdown="block">
### Print vs Return

__What's the difference between printing in a function and returning a value from a function? &rarr;__

{% highlight python %}
def greet(greeting, num):
	s = greeting * num
	print(s)

def greet(greeting, num):
	s = greeting * num
	return s
{% endhighlight %}
</section>

<section markdown="block">
### Print vs Return Continued

What's the difference between printing in a function and returning a value from a function?  

* __printing alone will not give you back a value for a function!__  
* however, you can print __and__ return
	* useful for debugging
	* see the example below... where we print out what s is before returning it

{% highlight python %}
def greet(greeting, num):
	s = greeting * num
	print(s)
	return s
{% endhighlight %}
</section>


<section markdown="block">
### Stopping Execution

The return statement stops execution of your function immediately.  __What gets printed in the following example? &rarr;__

{% highlight python %}
def foo():
	print("one")
	print("two")
	return "foo"
	print("three")

foo()
{% endhighlight %}
<div class="incremental" markdown="block">
"one" and "two" are printed, but three is not because the function has already returned the value "foo"
</div>
</section>

<section markdown="block">
### Another Example...

Stopping execution again...

{% highlight pycon %}
>>> def area(r):
...   a = math.pi * r * r
...   print("before return")
...   return a
...   print("after return")
... 
>>> area(6)
before return
113.09733552923255
{% endhighlight %}
</section>

<section markdown="block">
### Multiple Return Statements

You can have multiple return statements in your function!  __Write a function that calculates absolute value. &rarr;__

<div class="incremental" markdown="block">
{% highlight python %}
def absolute_value(x):
	if x >= 0:
		return x
	else:
		return x * -1
{% endhighlight %}
</div>
</section>

<section markdown="block">
### Some Exercises

* create a function that returns the largest factor of a number that isn't the number itself
* create two funcions: is_even and is_odd... 
	* each will take one argument (an int)
	* it will use modulo to determine if the number is even or odd
	* it will return True or False
	* (arguably easier to understand than just modulo alone)
* pluralize
	* just add s
	* special case
</section>

<section markdown="block">
## [And... Back to Strings](strings.html)
</section>
