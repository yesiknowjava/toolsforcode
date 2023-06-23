+++
title = "Python interview questions with answers"
description = "Growing list of python questions with simple answers"
featuredImage = "/img/python-interview-questions.jpg"
tags = ["code"]
categories = ["code"]
date = 2022-08-18T09:46:44.431Z
draft = false
+++

This is a growing list hence, the article has been broken down into multiple parts

<div class="category-widget" style="border: 1px solid #CCC; padding: 10px 0 0 10px">
        <ul>
                <li>[1. Python Interview questions part 1](../python-interview-questions-with-answers/)</li>
                <li>[2. Python Interview questions part 2](../python-interview-questions-with-answers-part2/)</li>
        </ul>
</div>
<p></p>

#### How to find the occurances of a particular substring in a sentance?
  
There are many ways of solving the problem.

1. Regular Expressions
2. Python in-built methods like count()
3. Custom Solutions using loops
  
  
_Regular Expression_


{{< highlight python >}}
x = "This is a new sentence with many sentences"
regex=re.compile(r"\bsentence\b")
regex.findall(x)
{{< / highlight >}}
<br>
    
The result would be a list of values with the exact match of the word '_sentence_'. Note that, since we use _```'\bword\b'```_, it wont find the word '_sentences_'. If you want 'sentences' too then all we have to make a small change to the regular expression 

{{< highlight python >}}
x = "This is a new sentence with many sentences"
regex=re.compile(r"sentence")
regex.findall(x)
{{< / highlight >}}
<p></p>
In the above case, it would give us a result of 2.

_Count Method_

"This is a new sentence with many sentences"_.count('sentence')_

This method counts all words and not just whole words

_Custom Solutuion_
We can loop through the words in the sentence and match the exact required word in each item

{{< highlight python >}}
l = 0
for i in s.split():
    if i == 'sentence':
        l += 1
print l
{{< / highlight >}}
<p></p>
There are many caveats to this, but you can get through the specifics once you know them.
<p></p>

#### How to join two lists where in if a is \[1,2] and b is \[3,4], we want the result as a single list of \[1,2,3,4] ?
<p></p>
{{< highlight python "linenos=table,linenostart=1" >}}
a = [1,2]
b = [3,4]
# solution 1
c = a.extend(b)
# solution 2
c = a + b
{{< / highlight >}}
<p></p>

#### Given a list of values \[1,2], how to get a result list which is like this \[1,2,1,2,1,2]
<p></p>
The solution to this problem is very simple.
{{< highlight python >}}
a = [1,2]
b = a*3
{{< / highlight >}}
<p></p>

#### What is the output of the following code
<p></p> 
{{< highlight python >}}
s = "COMPUTER"
print(s[-3:]) #prints TER
print(s[:-2]) #prints COMPUT
{{< / highlight >}}
<p></p>

#### What is the type of the variable a and b
<p></p>
{{< highlight python >}}
a = (1)
print(type(a))
b = (1,)
print(type(b))
{{< / highlight >}}
<p></p>
Variable 'a' although enclosed in paranthesis, making it actually look like a tuple, it indeed is an integer. It needs to have a comma at the end if it is a single item tuple to make it a tuple.

Hence type(a) is integer and type(b) would be a tuple

Note that the trailing comma is not required if there are more than one item in the tuple.
<p></p>

#### Given a string 'COW' I want the output "COWCOW", how to do that
<p></p>
{{< highlight python >}}
s = "COW"
print(s*2) #or
print(s+s)
{{< / highlight >}}
<p></p>
Incidentally a list can also be doubled like this

{{< highlight python >}}
a = [1,2,3,4]
b = a*2
print(b) # would output [1,2,3,4,1,2,3,4]
{{< / highlight >}}
<p></p>

#### Get index of an item while looping a list
<p></p>
We can use the enumerate method to do this

{{< highlight python >}}
a = [1,2,3,4]
for index, item in enumerate(y):
    print(index)
{{< / highlight >}}
<p></p>

#### Get the length of a list in python
<p></p>
We can use the len method to do this

{{< highlight python >}}
a = [1,2,3,4]
print(len(a)) #outputs 4
{{< / highlight >}}

we can use the same method on strings to get the number of characters in a string

{{< highlight python >}}
a = "abcd"
print(len(a)) #outputs 4
{{< / highlight >}}
<p></p>

#### What does the sorted function print in the following code
<p></p>

{{< highlight python >}}
a = sorted('cat')
b = sorted([3,2,1])
print(a) #outputs a list ['a','c','t']
print(b) #outputs a list [1,2,3]
{{< / highlight >}}


#### How to sort on the second letter of the word in a list of words in python
<p></p>

We can use the sorted method with an additional parameter

{{< highlight python >}}
z = ['kevin','nikolas','Jenny','Craig']
b = sorted(z, key=lambda k:k[1])
print(z) #outputs a list ['kevin','Jenny','nikolas','Craig']
{{< / highlight >}}
<p></p>

#### Explain count function in python
<p></p>
{{< highlight python >}}
x = 'hippo'
print(x.count('i')) # prints 2
y = ['cat', 'dog', 'cat']
y.count('cat') # prints 2
{{< / highlight >}}
<p></p>

#### Show the difference between append and extend
<p></p>
{{< highlight python>}}
a = [1, 2, 3]
a.append(4) # a has the value [1,2,3,4]
a.append([5,6]) # a has the value [1,2,3,4,[5,6]]

b = [1, 2, 3]
b.extend(4) # throws an error, int object is not iterable
b.extend([5,6]) # b has the value [1,2,3,4,5,6]

# the above can alse be done using
b+[5,6]
{{< / highlight >}}
<p></p>

#### Explain pop method in python
<p></p>
{{< highlight python >}}
x = ['cat', 'dog', 'cat']
y = x.pop() # y has the last element of the list
{{< / highlight >}}

We can also pop the list at a particular index

{{< highlight python >}}
x = ['cat', 'dog', 'cat']
y = x.pop(1) # y has the value 'dog'
{{< / highlight >}}
<p></p>

#### Explain the output of the following code
<p></p>
{{< highlight python >}}
x = []
y = x.pop()
{{< / highlight >}}

Throws "IndexError : pop from empty list"
<p></p>
{{< highlight python >}}
x = ['cat', 'dog', 'cat']
y = x.remove('cow')
{{< / highlight >}}

Throws "ValueError : 'cow' not in list"
<p></p>

#### Explain the difference between sort and sorted method
<p></p>
{{< highlight python >}}
x = [6,2,1,8,5]
x.sort()
print(x) # x is sorted

y = sorted(x)
print(x) # x is still unsorted
print(y)
{{< / highlight >}}

Sort method does an inplace sort, whereas sorted method takes an argument and returns a sorted list. Original item will still be unsorted.

<p></p>

#### How are tuples represented
<p></p>
{{< highlight python >}}
x = ()
x = 1,
x = (1,)
x = 1,2,3
x = tuple([1,2,4])
{{< / highlight >}}

<p></p>

#### Show some intersting facts about tuples
<p></p>
{{< highlight python >}}
x = 1,2,3
del x[0] # Throws error

x = ([1,2],3)
del x[0][1] # this deletes the item 2 and x will now be ([1],3)

x = (1,2,3)
x+=4, # Notice the comma after 4
print(x) # x is now (1,2,3,4)
{{< / highlight >}}

We really need to understand what immutable means. Strings are truly immuatable, but tuples seem to have some caveats.
<p></p>

#### What are sets and how are they represented
<p></p>
A set is a unique list of items without duplicates
{{< highlight python >}}
# sets are represented like so
x = {1,2,3} 
y = set()

x.add(4) # now x has {1,2,3,4}
x.add(4) # adding 4 again has no effect as it is already available in the set
s.clear() # clears all items
{{< / highlight >}}

Also, sets can be sorted using sorted function, but not sorted in place
{{< highlight python >}}
x = {4,3,2,9,8} 
y = sorted(x) # y is a sorted 'list' [2,3,4,8,9]
x.sort() # AttributeError: 'set' object has no attribute 'sort'
{{< / highlight >}}

<p></p>

#### How are dictionaries represented
<p></p>
There are many ways of representing a dictionary.

{{< highlight python >}}
x = {'apple':1,'orange':2}
x = dict([('apple',1), ('orange',2)])
x = dict(apple=1, orange=2)
{{< / highlight >}}

<p></p>

#### Difference between clear and del method
<p></p>

{{< highlight python >}}
x = {'apple':1,'orange':2}
x.clear()
print(x) # x is now {}
del x
print(x) # Throws an error saying 'x' is not defined
{{< / highlight >}}

While ```clear()``` clears the content of the dictionary, the variable is still intact. The ```del``` method removes the memory location of the variable and hence the variable becomes undefined.
<p></p>


#### Convert a dictionary into a list of tuples
<p></p>

{{< highlight python >}}
x = {1:1, 2:2, 3:3}
y = x.items() # y will be [(1, 1), (2, 2), (3, 3)]
{{< / highlight >}}

While ```clear()``` clears the content of the dictionary, the variable is still intact. The ```del``` method removes the memory location of the variable and hence the variable becomes undefined.
<p></p>

#### Get all positions of an item in a list
<p></p>

{{< highlight python >}}
names = ['krishna', 'rama', 'prabhakar', 'krishna', 'prabhakar']
idx = [k for k,v in enumerate(names) if v == 'krishna']
print(idx)

# To remove all occurances of an item in a list
new_name_list = [i for i in in if i != 'prabhakar']

{{< / highlight >}}
<p></p>

#### Implement a queue in python
<p></p>

{{< highlight python >}}
from collections import deque
mq = deque()
mq.append(5)
mq.append(15)
print(mq) # prints .. deque([5, 15])
mq.popleft() # outputs the value 5
{{< / highlight >}}
<p></p>

#### Explain the output of the following program
<p></p>

{{< highlight python >}}
class Protected:
    __name = "not accessible"
    def __method(self):
        return self.__name

prot = Protected()
prot.__name # no attribute error
prot.__method() # no attribute error
{{< / highlight >}}
<p></p>

Anything that starts with a double __ will be protected by python. Internally the variables that start with __ actually becomes ```_Protected__variable```.

For example, ```__name``` becomes ```_Protected__name```

This can be known by using the ```dir(prot)``` command, which lists all variables and methods of the class (irrespective of whether they are protected or not)


Please have a look at the other parts of the same article
<div class="category-widget" style="border: 1px solid #CCC; padding: 10px 0 0 10px">
        <ul>
                <li>[1. Python Interview questions part 1](../python-interview-questions-with-answers/)</li>
                <li>[2. Python Interview questions part 2](../python-interview-questions-with-answers-part2/)</li>
        </ul>
</div>
<p></p>