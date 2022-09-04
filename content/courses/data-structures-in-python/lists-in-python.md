+++
type="courses"
layout="courses"
title = "Lists"
sub="true"
description = "List is a sequence of objects like strings, numbers or other lists. This chapter explains how a list is used."
image = "/img/python-interview-questions.jpg"
featuredImage = "/img/python-interview-questions.jpg"
tags = []
categories = []
date = 2022-08-18T09:46:44.431Z
draft = false
weight = 1
+++
A list is a sequence of objects that can hold strings, numbers, objects and other lists too.

A list is represented using the ```[]``` brackets.

{{< highlight python >}}
a = [1,2,3]
b = [1, 'string', {1:1}, a] #lists can have anything in them
{{< / highlight >}}
  

Lists are mutable and they cannot be used as a key for dictionaries.

Common List methods are

1. 1. ```append()``` - Adds an element to the end of the list
2. 2. ```clear()``` - Removes all the elements from the list
3. 3. ```copy()``` - Returns a copy of the list
4. 4. ```count()``` - Returns the number of elements with the specified value
5. 5. ```extend()``` - Add the elements of a list (or any iterable), to the end of the current list
6. 6. ```index()``` - Returns the index of the first element with the specified value
7. 7. ```insert()``` - Adds an element at the specified position
8. 8. ```pop()``` - Removes the element at the specified position
9. 9. ```remove()``` - Removes the item with the specified value
10. 10. ```reverse()``` - Reverses the order of the list
11. 11. ```sort()``` - Sorts the list
<p></p>
Note : The ```remove``` method will throw an eror if the item does not exist in the list. The ```pop``` method will throw an error if the list is empty.
<p></p>

##### Lets solve a problem using lists
<p></p>

Given a list of temperatures ```[73, 74, 75, 71, 69, 72, 76, 73]``` for each day, can we find how many days it will take to get a warmer day than the present day. In our case it should print a list ```[1, 1, 4, 2, 1, 1, 0, 0]```

{{< highlight python >}}
def get_next_best_list(i, temp_list, bst_list):
    counter = 0
    found = False
    if temp_list:
        for item in temp_list:
            counter += 1
            if item > i:
                found = True
                break
    if found:
        bst_list.append(counter)
    else:
        bst_list.append(0)
    
    if len(temp_list):
        return get_next_best_list(temp_list.pop(0), temp_list, bst_list)
    else:
        return bst_list

if __name__ == "__main__":
    temp_list = [73, 74, 75, 71, 69, 72, 76, 73]
    bst_list = get_next_best_list(temp_list.pop(0), temp_list, [])
    print(bst_list)
{{< / highlight >}}
<p></p>
The logic is pretty much straight forward. First we call the get_next_best_list method with 3 parameters viz: the first item of the list, then the entire list itself and the last parameter (a list) which will hold the list of days to wait for warmer temperature. That would be empty initially.

<p></p>

##### How to get the combination of all possible values in a given list say ```[1,2,3]```. This should get all possible permuations like ```[1], [2], [3], [1,2], [1,3], [2,1], [2,3],[2,1,3], [3,2,1]``` etc
<p></p>

__Method 1__
{{< highlight python >}}
def perm1(lst):
	if len(lst) == 0:
		return []
	elif len(lst) == 1:
		return [lst]
	else:
		l = []
		for i in range(len(lst)):
			x = lst[i]
			xs = lst[:i] + lst[i+1:]
			for p in perm1(xs):
				l.append([x] + p)
		return l
{{< / highlight >}}
<p></p>

__Method 2__
{{< highlight python >}}
def combs(a):
    if len(a) == 0:
        return [[]]
    cs = []
    for c in combs(a[1:]):
        
        cs += [c, c+[a[0]]]   
        print(cs)
    return cs
{{< / highlight >}}
<p></p>

__Method 3 : Python's inbuilt tool__
{{< highlight python >}}
# Function which returns subset or r length from n 
from itertools import combinations 

def rSubset(arr, r): 

	# return list of all subsets of length r 
	# to deal with duplicate subsets use 
	# set(list(combinations(arr, r))) 
	return list(combinations(arr, r)) 

if __name__ == "__main__": 
	arr = [1, 2, 3, 4] 
	r = 2
	print rSubset(arr, r) 

{{< / highlight >}}
<p></p>