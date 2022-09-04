+++
title = "Python interview questions with answers part 2"
description = "Growing list of python questions with simple answers"
image = "/img/python-interview-questions-part2.jpg"
featuredImage = "/img/python-interview-questions-part2.jpg"
tags = ["code"]
categories = ["code"]
date = 2022-08-04T00:46:44.431Z
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


#### Fibonacci series in python?
  
Generate a Fibonacci series for a given number

{{< highlight python >}}
a,b,n = 0,1,10
for i in range(0, n):
    print(a, end=', ')
    a, b = b, a+b
{{< / highlight >}}
<br>

#### Check if a string is a palindrome or not

There are many ways of implementing this.

__String Reverse__
{{< highlight python >}}
mystring = 'malayalam'
reverse_mystring = mystring[::-1]
reverse_mystring = ''.join(reversed(mystring))

if  mystring == reverse_mystring:
    print("String is a palindrome")
else:
    print("String is NOT a palindrome")
{{< / highlight >}}

<p></p>

__String Reverse__
{{< highlight python >}}
def isPalindrome(str):
    for i in range(0, len(str)//2):
        if str[i] != str[len(str)-i-1]:
            return False
    return True
{{< / highlight >}}




#### If you have multiple decorators for a function, which would be called first

{{< highlight python >}}
def a(f):
    def wrapperxx(*args, **kwargs):
        print("a")
        f(*args, **kwargs)
    return wrapperxx

def b(f):
    def wrapperxx(*args, **kwargs):
        print("b")
        f(*args, **kwargs)
    return wrapperxx

def c(f):
    def wrapperxx(*args, **kwargs):
        print("c")
        f(*args, **kwargs)
    return wrapperxx

@a
@b
@c
def myfunction(a):
    print(a)
myfunction("Prabhakar")
{{< / highlight >}}

The result would be

{{< highlight python >}}
a
b
c
Prabhakar
{{< / highlight >}}


This is a growing list hence, the article has been broken down into multiple parts

<div class="category-widget" style="border: 1px solid #CCC; padding: 10px 0 0 10px">
        <ul>
                <li>[1. Python Interview questions part 1](../python-interview-questions-with-answers/)</li>
                <li>[2. Python Interview questions part 2](../python-interview-questions-with-answers-part2/)</li>
        </ul>
</div>
<p></p>