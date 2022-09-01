+++
type="courses"
layout="courses"
title = "Dictionaries"
sub="true"
description = "What is a dictionary. Dictionary implementation in python and its use cases."
image = "/img/python-interview-questions.jpg"
featuredImage = "/img/python-interview-questions.jpg"
tags = []
categories = []
date = 2019-10-18T09:46:44.431Z
draft = false
weight = 2
+++

A dictionary is a hash map contaning key value pairs. In python dictionaries are represented like this

{{< highlight python "linenos=table" >}}
dt = {
    'apples': 2,
    'oranges': 5
}
{{< / highlight >}}
  
One thing to note here is that, dictionaries are great for searching as the order of complexity is always ```Big O(1)```.
  
You can use strings, numbers or tuples as keys for dictionaries like so

{{< highlight python "linenos=table" >}}
dt = {
    1: 1,
    'astring': 2,
    (1,2,3): 1
}
{{< / highlight >}}
  
This is great. Now lets try and solve some problems using dictionaries.

Given a list of values ```data = [[1, 5, [2, 3]], [2, 3, [4]], [3, 3, []], [4, 2, []]]``` with each item in the list representing empid, his value and finally his subordinate list, can we try to find the total value of an employee along with the value of his subordinates if he has one.

Suppose we want the net asset value (nav) of emp id 1, that would be 5 + 3 + 3 + 2 = 13. Note that the value of empid 4 is also included, even though he is not directly related to emp id 1.

Solution : The best way to solve this problem is to first convert the list into a dict.

{{< highlight python "linenos=table" >}}
def form_dict(data):
    data_dict = {}
    for item in data:
        data_dict[item[0]] = {
            'worth': item[1],
            'subordinate_ids': item[2]
        }
    return data_dict
{{< / highlight >}}

Next we try to create a list with the value of each employee involved, by calling a recursive function.

{{< highlight python "linenos=table" >}}
def calculate_worth(data_dict, id, worth_list=[]):
    try:
        worth_list.append(data_dict[id]['worth'])
        if data_dict[id]['subordinate_ids']:
            for sub_id in data_dict[id]['subordinate_ids']:
                calculate_worth(data_dict, sub_id, worth_list)
    except:
        print("Unexpected error: invalid key")
    return worth_list
{{< / highlight >}}

The function calvulate_worth takes 3 arguments, 

1. 1. the dictionary containing the employee details
2. 2. the employee id for which we need the value of
3. 3. worth_list, a list containing the value of each employee and his subordinates.

  
  
worth_list is the final output. It is initially sent as an empty list.


The method tries to append the net asset value of the employee to worth_list first and if the employee has subordinates, it then calls itself recursively with the id of each of the subordinates if the employee has one. If the employee has no subordinates, it just adds the value of the employee to the worth_list list and quits.