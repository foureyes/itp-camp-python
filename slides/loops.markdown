---
layout: slides
title: Loops
---

<section markdown="block">
# Loops
{% include title-slide-footer.html %}
</section>

<section markdown="block" class="title-slide">
## While Loops 
</section>

<section markdown="block">
### Write a Program to Print out the numbers 1 through 9

Seems easy enough...
</section>

<section markdown="block">
### Motivation for Loops

A program to count from 1 to 9:

{% highlight python %}
n, delta = 1, 1
print(n)
n = n + delta
print(n)
n = n + delta
print(n)
n = n + delta
print(n)
n = n + delta
print(n)
n = n + delta
print(n)
n = n + delta
print(n)
n = n + delta
print(n)
n = n + delta
print(n)
{% endhighlight %}
</section>

<section markdown="block">
### Motivation for Loops Continued

Um.  That was _kind of tedious_.  Can't we just tell the computer to repeat those two lines of code?  

__YES! ...using loops__

{% highlight python %}
n = 1
end = 9
delta = 1

while n <= end:
	print(n)
	n = n + delta
{% endhighlight %}
</section>

<section markdown="block">
### Iteration and Loops

Some formal definitions:

* __iteration__ - repeated execution of a set of programming statements.
* __loop__ - the construct that allows us to repeatedly execute a statement or a group of statements until a terminating condition is satisfied.
* sometimes these words are used interchangeably
</section>

<section markdown="block">
### While Loops

Using a __while__ loop allows us to:

* repeat a block of code
* ...as long as a condition is met
* stops as soon as the condition is no longer true
* looks similar to an if statement
</section>

<section markdown="block">
### While Loop Syntax

A template:

{% highlight python %}
# while <some sort of condition>:
#	<do stuff here>
{% endhighlight %}

Some _real_ code:

{% highlight python %}
a = 100
while a > -1:
	print(a)
{% endhighlight %}

__What does this output? &rarr;__

<div class="incremental">
{% highlight python %}
100
100
100
{% endhighlight %}
</div>
</section>

<section markdown="block">
### Trivial Cases, Again

__What do these snippets of code print out?&rarr;__
{% highlight python %}
while True:
	print("I'm true!")
{% endhighlight %}
{% highlight python %}
while False:
	print("I'm false!")
{% endhighlight %}

<div class="incremental">
{% highlight python %}
I'm true!
I'm true!
I'm true!
{% endhighlight %}
{% highlight python %}
# nothing printed here
{% endhighlight %}
</div>
</section>

<section markdown="block">
### Let's Step Through True
{% highlight python %}
while True:
	print("I'm true!")
{% endhighlight %}

1. condition is true
2. print "I'm true!"
3. go back to top
4. condition is true
5. print "I'm true!"
6. go back to top
7. you know the _deal_
</section>

<section markdown="block">
### Let's Step Through False
{% highlight python %}
while False:
	print("I'm false!")
{% endhighlight %}

1. condition is false

We never even get into the body of the loop!
</section>

<section markdown="block">
### Slightly More Complicated
<aside>Well, Not This One Exactly, But You'll See</aside>

__What does this print out? &rarr;__

{% highlight python %}
keep_on_going = True
while keep_on_going:
	print("I'm going!)"
{% endhighlight %}

<div class="incremental">
{% highlight python %}
I'm going
I'm going
I'm going
.
.
I'm going
{% endhighlight %}
</div>
</section>

<section markdown="block">
### Slightly More Complicated Continued

__Let's add one line.  What does this print out? &rarr;__

{% highlight python %}
keep_on_going = True
while keep_on_going:
	print("I'm going!")
	keep_on_going = False
{% endhighlight %}

<div class="incremental">
{% highlight python %}
I'm going
{% endhighlight %}
</div>
</section>

<section markdown="block">
### Slightly More Complicated Continued Continued

Going through each iteration

{% highlight python %}
keep_on_going = True
while keep_on_going:
	print("I'm going!")
	keep_on_going = False
{% endhighlight %}

* condition (keep_on_going) is true 
* print "I'm going!"
* set keep_on_going to false
* condition (keep_on_going) is false

Loop ends after one iteration.
</section>

<section markdown="block">
### What Happened There?

* we had some state __outside__ of the loop
* __within__ the loop we mutated / changed that state to eventually get out of the condition
* consequently, the loop _terminates_
* sometimes we call these kinds of variables __sentinel__ variables
* they only let certain conditions in!
</section>

<section markdown="block">
### Affecting the Outcome of the Condition

To change the outcome of your conditional:

* maintain state 
	* declare a variable __outside__ of the loop!
* mutate that state on loop iteration 
	* change that variable __inside__ the loop!
	* this will eventually cause the conditional to fail
* examples:
	* using operators to change a variable in your condition
	* using input to change a variable in your condition
</section>


<section markdown="block">
### Count From 2 Through 8 By 2's

__How would you implement this?&rarr;__

<div class="incremental">
{% highlight python %}
count = 2
while count <= 8:
	print(count)
	count = count + 2
{% endhighlight %}
</div>
</section>

<section markdown="block">
### Stepping Through Counting By 2's
{% highlight python %}
count = 2
while count <= 8:
	print(count)
	count = count + 2
{% endhighlight %}
1. count is 2
2. condition is true because count (2) is less than 8
3. print count
4. add 2 to count... count is now 4
5. condition is true because count(4) is less than 8..
6. goes on until count gets to 10, at which point condition is no longer true

[Check out the fancy step through](http://www.pythontutor.com/visualize.html#code=count+%3D+0%0Awhile+count+%3C%3D+8%3A++++%0A++++print(count)%0A++++count+%3D+count+%2B+2&mode=display&cumulative=false&py=2&curInstr=0)
</section>

<section markdown="block">
### Odd Numbers Except 13

__Write a program that... &rarr;__

* prints all of the odd numbers from 1-99
* skips 13

There are a few ways to do this!  __What are some general strategies for solving this problem?&rarr;__

<div markdown="block" class="incremental">

* using modulo
* or incrementing by twos

</div>
</section>

<section markdown="block">
### Possible Solutions for Odd Numbers Except 13
 
[Increment by 2's](http://www.pythontutor.com/visualize.html#code=n+%3D+1%0Awhile+n+%3C%3D+99%3A%0A++++if+n+!%3D+13%3A%0A++++++++print(n)%0A++++n+%3D+n+%2B+2&mode=display&cumulative=false&heapPrimitives=false&drawParentPointers=false&textReferences=false&py=3&curInstr=0)

{% highlight python %}
n = 1
while n <= 99:
    if n != 13:
        print(n)
    n = n + 2
{% endhighlight %}

[Using modulo to determine odds](http://www.pythontutor.com/visualize.html#code=n+%3D+1%0Awhile+n+%3C%3D+99%3A%0A++++if+n+!%3D+13%3A%0A++++++++print(n)%0A++++n+%3D+n+%2B+2&mode=display&cumulative=false&heapPrimitives=false&drawParentPointers=false&textReferences=false&py=3&curInstr=0)

{% highlight python %}
n = 1
while n <= 99:
    if n % 2 == 1 and n != 13:
        print(n)
    n = n + 1
{% endhighlight %}
</section>

<section markdown="block">
### Do You Want Cake (Again)

__Repeatedy ask if user wants cake until user says yes or yeah.  How would you implement this?&rarr;__

{% highlight python %}
Do you want cake?
> no
Do you want cake?
> No
Do you want cake?
> yeah
Have some cake!
{% endhighlight %}

<div class="incremental">
{% highlight python %}
answer = 'no'
while answer != 'yes' and answer != 'yeah':
	answer = raw_input("Do you want cake?\n> ")
print("Have some cake!")
{% endhighlight %}
</div>
</section>

<section markdown="block">
### Stepping Through Cake

Let's make an assumption that the user enters "no" first, and then "yeah" second.

{% highlight python %}
answer = 'no'
while answer != 'yes' and answer != 'yeah':
	answer = raw_input("Do you want cake?\n> ")
print("Have some cake!")
{% endhighlight %}

1. answer is set to no by default
2. condition is true, answer (no) is not 'yes' or 'yeah'
3. answer is set to user input of 'no'
4. condition is true, answer (no) is not 'yes' or 'yeah'
5. answer is set to user input of 'yes'
6. condition is false, answer != 'yeah' is now false!
7. have some cake is printed
</section>

<section markdown="block">
### Accumulating Values

__Write a program that will: &rarr;__ 

* continually ask the user for a number (__forever__)
* add that number to a running total
* print out the running total

{% highlight python %}
Give me a number to add
> 10
Current total is 10
Give me a number to add
> 15
Current total is 25
Give me a number to add
> 5
Current total is 30
Give me a number to add
> 
{% endhighlight %}

</section>

<section markdown="block">
### Potential Solution for Accumulating Values

{% highlight python %}
total = 0
while True:
    n = int(raw_input("Give me a number to add\n> "))
    total = total + n
    print("Current total is " + str(total))
{% endhighlight %}

</section>

<section markdown="block">
### A Difficult One... 

__Write a program that continually asks the user for numbers, and asks them if they'd like to keep going.  In the end, it should output the average of all of the numbers entered&rarr;__

{% highlight python %}
I'll calculate the average for you!
Current total: 0
Numbers summed: 0
Please enter a number to add
> 10
Do you want to continue adding numbers (yes/no)?
> yes
Current total: 10
Numbers summed: 1
Please enter a number to add
> 12
Do you want to continue adding numbers (yes/no)?
> no
The average is 11.0
{% endhighlight %}
</section>

<section markdown="block">
### Some Hints, Please?
Let's try keeping track of multiple variables:

* a user's answer to whether or not the program should continue
* the total (sum) of the numbers that a user has entered 
* the count of numbers input
</section>

<section markdown="block">
### An Average Solution

{% highlight python %}
total = 0
count = 0
answer = 'yes'
print("I'll calculate the average for you!")
while answer == 'yes':
        print("Current total: " + str(total))
        print("Numbers summed: " + str(count))
        total = total + int(raw_input("Please enter a number to add\n> "))
        count = count + 1
        answer = raw_input("Do you want to continue adding numbers (yes/no)?\n> ")
print("The average is "+ str(total / count))
{% endhighlight %}
</section>

<section markdown="block">
### Increment / Decrement

We've used the following syntax to increment or decrement a variable

{% highlight python %}
n = 0
n = n + 1

n = 100
n = n - 1
{% endhighlight %}

_Slightly_ tedious...
</section>

<section markdown="block">
### Increment / Decrement Continued

There's some _syntactic sugar_ that makes doing this less verbose:  use __+=__ or __-=__

* __n += 1__ is the same as n = n + 1
* __n -= 1__ is the same as n = n - 1

{% highlight python %}
n = 0
# adds one to n and binds the resulting value to n
n +=  1

n = 100
# subtracts one to n and binds the resulting value to n
n -= 1
{% endhighlight %}

</section>

<section markdown="block">
### More Syntactic Sugar

This works for other operators too.   __What does this code print out? &rarr;__

{% highlight python %}
n = 2
n *= 2
n *= 2
print(n)

n = 64
n /= 2
n /= 2
print(n)
{% endhighlight %}
<div class="incremental">
{% highlight python %}
8
16.0
{% endhighlight %}
</div>

</section>

<section markdown="block">
### What About Strings?

Also works with strings....   __What does this code print out? &rarr;__
{% highlight python %}
s = "h"
s += "e"
s += "y"
s *= 3
print(s)
{% endhighlight %}

<div class="incremental">
{% highlight python %}
heyheyhey
{% endhighlight %}
</div>

<!-- remove asterisk* -->
</section>

<section markdown="block">
### Other Exercises

* count the number of digits in an int
	* repeatedly use integer division
	* ...until the original number becomes 0
	* keep count of divisions
* continually add exclamation points to a word
	* ask for a word
	* ask for x number of exclamation points
	* print out resulting word and exclamation points
	* continue asking for another word and exclamation points
</section>

<section markdown="block" class="title-slide">
# For Loops
{% include title-slide-footer.html %}
</section>

<section markdown="block">
### Loops, In General

Does anyone remember the two broad  __categories__ of loops?  __What are they, and how are they different?__ &rarr;

<div class="incremental" markdown="block">
* __condition-controlled__ - repeats as long as a condition is true
* __count-controlled__ - repeats a specific number of times
</div>
</section>

<section markdown="block">
### Condition Controlled Loops in Python

__What programming construct (repetition structure) do we use in Python to create a condition-controlled loop?__ &rarr;

<div class="incremental" markdown="block">
A __while__ loop is a repetition structure in Python that repeats a block of code as long as a check for a particular condition is true.
</div>
</section>

<section markdown="block">
## Count-Controlled Loops

<aside>In Python, <em>for loops</em> are count-controlled loops.</aside>

</section>

<section markdown="block">
### For Loops

An Example

{% highlight python %}
for i in range(5):
	print(i)
{% endhighlight %}

Its output:

{% highlight python %}
0
1
2
3
4
{% endhighlight %}
</section>


<section markdown="block">
### For Loop Syntax

__for loops__ repeat code by iterating over every item in some group / collection of items:

{% highlight python %}
"""
for <loop variable> in <iterable object>:
	(<loop variable> can be used here)
"""

{% endhighlight %}

Again, the same example:

{% highlight python %}
"""
 keyword    loop    an iterable object,
     for  variable  like range
       |     |      |
       |     |      |
        for i in range(5):
              print(i)
"""
{% endhighlight %}
</section>

<section markdown="block">
### Let's Break That Down a Bit

A __for__ loop:

* consists of the keyword __for__ (obvs!)
* followed by a __loop variable__ (this could be named anything you like)
* followed by some __iterable object__ (some sequence of values)
* followed by a colon
* in this case, the iterable object is returned by the __range__ function
* the range function returns an arithmetic sequence of numbers
* in this case, that sequence is [0, 1, 2, 3, 4]
</section>


<section markdown="block">
## For Loops - Details, Details, Details
</section>

<section markdown="block">
### What Does It Do?

A __for__ loop:

* repeats a block of code for a specific number of times
* it does this by running through all of the elements in a sequence, one at a time
* the current element can be accessed in the body of the for loop using the __loop variable__
* (note that the __loop variable__ is called __target variable__ in {{ site.bookq }})
* that is... for each element in your sequence, the __loop variable__ is set to that element
</section>

<section markdown="block">
### For Loops

A more technical explanation is: __for loops__ iterate over every item in an __iterable object__.  

An _iterable object_:

* is a _thing_ (_object_) that contains other values / _members_
* is capable of returning each of its members __one at a time__
* examples of iterable objects include: 
	* strings (we know these)
	* __range objects__ (we'll learn these today)
	* lists (for the future!)
* so... let's see about these __range objects__
</section>

<section markdown="block">
### Range and Range Objects

A __range__ object is another data type!  It represents an _arithmetic sequence_, such as 0, 1, 2, 3, 4.

* a __range__ object is created by calling the range() function.
* with one argument, it creates an arithmetic sequence from 0 up to but __not including__ that argument
* consequently, range(5) produces 0, 1, 2, 3, 4
* to see the elements in a range, you can use the __list()__ function
* (we'll learn more about lists later!)
</section>

<section markdown="block">
### Showing the Results of Range

__Let's see if we can make sense of this:__ &rarr;

{% highlight python %}
# make a range object - an arithmetic sequence from 0 through 5
numbers = range(5)

# let's look at that object
print(numbers)

# what type is it?
print(type(numbers))

# can we actually see the sequence?  yes, but we have to use list.
print(list(numbers))
{% endhighlight %}

<div class="incremental" markdown="block">
{% highlight python %}
range(0, 5)
<class 'range'>
[0, 1, 2, 3, 4]
{% endhighlight %}
</div>
</section>

<section markdown="block">
### So... All of That Meant...

* there's a type called __range__
* the string representation of a range shows you the original arguments that you passed in
* you can call the built-in __list__ function (used to convert value into a list) to show the exact ints in the list
</section>

<section markdown="block">
### Quick Summary So Far...

We've learned two new built in functions

* __range__ returns a range _object_, a representation of an arithmetic sequence
* __list__ returns a list _object_
	* for now, we use list in combination with print  to show each number in a range object
	* we'll learn more about lists later
</section>

<section markdown="block">
## Range Life...

<aside>The built-in function, range(), creates range objects - convenient, eh?</aside>
</section>

<section markdown="block">
### Range 

__range()__ returns a __range object__, an arithmetic sequence of numbers.  

* one argument: __range__(stop) 
	* returns a series of numbers starting with 0, up to, but not including _stop_ by ones
	* range(3) &rarr; 0, 1, 2
* two arguments: __range__(start, stop) 
	* returns a series of numbers starting with _start_ , up to, but not including _stop_ by ones
	* range(5, 10) &rarr; 5, 6, 7, 8, 9
* three arguments: so many arguments, you'll have to go to the next slide &rarr;
</section>

<section markdown="block">
### Range (Continued)

(continued from previous slide)

* three arguments: __range__(start, stop, step)
	* returns a series of numbers starting with _start_ , up to, but not including _stop_ by _step_
	* range(4, 9, 2) &rarr; 4, 6, 8
</section>

<section markdown="block">
### Some Other Things You Should Know About Range

* negative _step_ goes backwards
	* range(8, 3, -2) &rarr; 8, 6, 4
* printing the result of a range object just gives you the original arguments that you used to call range
	* print(range(8, 3, -2)) &rarr; range(8, 3, -2)
* use the list function to show the elements in a range
	* print(__list__(range(8, 3, -2)))
</section>

<section markdown="block">
### Guess That Series of Numbers
<aside>Fun!</aside>

__Given the following calls to the range function, what is the start, stop, and step?  What is the resulting arithmetic sequence? &rarr;__

<div class="incremental" markdown="block">
{% highlight python %}
range(3)
{% endhighlight %}
{% highlight python %}
# start:0, end:3, step:1
0, 1, 2
{% endhighlight %}

{% highlight python %}
range(10, 16)
{% endhighlight %}
{% highlight python %}
# start:10, end:16, step:1
10, 11, 12, 13, 14, 15
{% endhighlight %}

{% highlight python %}
range(-2, 3)
{% endhighlight %}
{% highlight python %}
# start:-2, end:3, step:1
-2, -1, 0, 1, 2
{% endhighlight %}

</div>
</section>

<section markdown="block">
### Guess That Series of Numbers
<aside>MORE Fun!</aside>

__What is the start, stop, and step?  What is the resulting arithmetic sequence? &rarr;__

<div class="incremental" markdown="block">

{% highlight python %}
range(200, 501, 100)
{% endhighlight %}
{% highlight python %}
# start:200, end:501, step:100
200, 300, 400, 500
{% endhighlight %}

{% highlight python %}
range(0, 10, 5)
{% endhighlight %}
{% highlight python %}
# start:0, end:10, step: 5
0, 5
{% endhighlight %}

{% highlight python %}
range(5, -11, -5)
{% endhighlight %}
{% highlight python %}
# start:5, end:-11, step:-5
5, 0, -5, -10
{% endhighlight %}
</div>
</section>


<section markdown="block">
## For Loop Examples
</section>

<section markdown="block">
### And Now, Back to For Loops
<aside>A Slightly Different Example</aside>

{% highlight python %}
for whatevs in range(1, 4):
		print(str(whatevs) + " Mississippi")
{% endhighlight %}

* notice the different loop variable name, _whatevs_?
* __What does this snippet of code output?__

<div class="incremental" markdown="block">
{% highlight python %}
1 Mississippi
2 Mississippi
3 Mississippi
{% endhighlight %}
</div>
</section>

<section markdown="block">
### Let's Take a Closer Look

{% highlight python %}
for whatevs in range(1, 4):
		print(str(whatevs) + " Mississippi")
{% endhighlight %}

__Going over this step-by-step, what is the value of whatevs, and what is printed? &rarr;__

<div class="incremental" markdown="block">
* range(4) gives a sequence of 1, 2, 3
* first iteration, the loop variable, whatevs, is 1
* "1 Mississippi" is printed
* next iteration, the loop variable, whatevs, is 2
* "2 Mississippi" is printed
* next iteration, the loop variable, whatevs is 3
* "3 Mississippi" is printed
</div>
</section>

<section markdown="block">
### Another For Loop Example
{% highlight python %}
for num in range(6, 13, 3):
	result = num * num
	print(str(num) + " squared is " + str(result))
{% endhighlight %}

__And... step-by-step, that's: &rarr;__

<div class="incremental" markdown="block">
* the sequence is 6, 9, 12
* __num__: 6, __result__: 36, 6 squared is 36
* __num__: 9, __result__: 81, 9 squared is 81
* __num__: 12,__result__: 144, 12 squared is 144

[And by using pythontutor.com](http://www.pythontutor.com/visualize.html#code=for+num+in+range(6,+13,+3)%3A%0A++++result+%3D+num+*+num%0A++++print(str(num)+%2B+%22+squared+is+%22+%2B+str(result))&mode=display&cumulative=false&heapPrimitives=false&drawParentPointers=false&textReferences=false&py=3&curInstr=0)
<!-- stop it* -->
</div>
</section>

<section markdown="block">
### How About Another?

__What is the output of this code? Let's read through it line-by-line to figure it out. &rarr;__

{% highlight python %}
for whatevs in range(1, 4):
	if whatevs == 2:
		print("let's skip this one")
	else:
		print(str(whatevs) + " Mississippi")
{% endhighlight %}

<div class="incremental" markdown="block">
{% highlight python %}
1 Mississippi
let's skip this one
3 Mississippi
{% endhighlight %}
[And again, step-by-step](http://www.pythontutor.com/visualize.html#code=for+whatevs+in+range(1,+4)%3A%0A++++if+whatevs+%3D%3D+2%3A%0A++++++++print(%22let's+skip+this+one%22)%0A++++else%3A%0A++++++++print(str(whatevs)+%2B+%22+Mississippi%22)&mode=display&cumulative=false&heapPrimitives=false&drawParentPointers=false&textReferences=false&py=3&curInstr=0)
</div>
</section>


<section markdown="block">
## For Loop Exercises
</section>

<section markdown="block">
### Some Quick Excercises

__Let's do these together &rarr;__

* count to 100 starting from 1
* count to 100 by twos from 0
* count backwards starting from 100 down to and including 0
</section>

<section markdown="block">
### Fizz Buzz
* [fizz buzz](http://c2.com/cgi/wiki?FizzBuzzTest)
* print out 1 to 100 ...with the following exceptions:
* for multiples of three, print out "Fizz" instead of the number 
* for multiples of five, print out "Buzz" instead of the number
* for multiples of both three and five print “FizzBuzz”
* example output, next slide, plz!
</section>

<section markdown="block">
### FizzBuzz Output
{% highlight python %}
1
2
Fizz
4
Buzz
Fizz
.
.
14
FizzBuzz
16
.
.
98
Fizz
Buzz
{% endhighlight %}
</section>

<section markdown="block">
### FizzBuzz Solution
{% highlight python %}
{% include classes/09/fizzbuzz.py %}
{% endhighlight %}
</section>

<section markdown="block">
## Using an Accumulator Variable
</section>

<section markdown="block">
### Accumulator Variable

An __accumulator__ variable is a variable used to keep the running total of a repeated calculation or operation that's within a loop:  

* a variable is declared outside of the loop
* it is added to within the loop

Some examples include:

* counting the number of times a while loop runs (count += 1)
* incrementally building a string within a loop (s += word)
</section>

<section markdown="block">
### Summing Numbers
* sum the first 1-100 numbers, print out the resulting the sum 
* (which, of course, [doesn't need a loop](http://betterexplained.com/articles/techniques-for-adding-the-numbers-1-to-100/))
* (and there's [this story](http://en.wikipedia.org/wiki/Carl_Friedrich_Gauss#Anecdotes))
* (and [the list of things named after him!?](http://en.wikipedia.org/wiki/List_of_things_named_after_Carl_Friedrich_Gauss))

<div class="incremental" markdown="block">
{% highlight python %}
{% include classes/09/sum.py %}
{% endhighlight %}
</div>
</section>

<section markdown="block">
### Counting Dice For Loop

__Roll a die 1000 times; count how many times a one is rolled!  Print out the result.  Use a for loop.&rarr;__

<div class="incremental" markdown="block">
{% highlight python %}
{% include classes/09/roll_for.py %}
{% endhighlight %}
</div>
</section>

<section markdown="block">
### Counting Dice While Loop

__Roll a die 1000 times; count how many times a one is rolled!  Print out the result.  Use a while loop.&rarr;__

<div class="incremental" markdown="block">
{% highlight python %}
{% include classes/09/roll_while.py %}
{% endhighlight %}
</div>
<!--_ -->
</section>

<section markdown="block">
## Using User Input to Influence Number of Repetitions
</section>

<section markdown="block">
### Controlling a For Loop With User Input

We can base the number of repetitions that a for loop goes through by asking the user to enter a value.

__Let's check out a programming problem where this idea might come in handy...__ &rarr;


</section>

<section markdown="block">
### A Ladder

__Make me a ladder!__ &rarr;

* ask for a height, make a ladder with that many rungs
* can you do this using a for loop?
* or how about just string multiplication?

{% highlight python %}
How tall do you want this ladder to be?
> 3

 ========
 |      |
 ========
 |      |
 ========
 |      |
{% endhighlight %}
</section>

<section markdown="block">
### A Ladder Implementation

(Or... two implementations, really)
{% highlight python %}
height = int(raw_input('How tall do you want this ladder to be?'))

for i in range(height):
	print('========\n|      |')

# or... just multiply instead of using the for loop
# print(height * '========\n|      |')
{% endhighlight %}
</section>
