---
title: "How to Rename a Duplicate Column in Django"
date: 2018-11-17T08:27:31+05:30
draft: false
categories: ["code"]
tags: ["e-learning"]
featuredImage: "img/code/rename-duplicate-column-in-django.jpg"
Description: "How to rename a duplicate column in django using orm or using raw queries."
---

Suppose you have a model where there is a column, say 'program_name' that is duplicated

The structure of the model is like this

    class Program(models.Model):

	    program_name = models.CharField(max_length=100)

	    currency = models.CharField(max_length=3)

Data for the sample model

| id | program_name  | currency |
|----|---------------|----------|
| 1  | demoprogram   | EUR      |
| 2  | demoprogram   | USD      |
| 3  | sampleprogram | USD      |

<br />

We can see that program_name 'demoprogram' is repeated twice, and for whatsoever reason you would like to rename them.

You can take the duplicate programs out using django orm like so,

    duplicate_programs = Program.objects.values('program_name').annotate(counter=Count('program_name')).filter(counter__gt = 1)

But the result would be a QuerySet without the id to take action

    <QuerySet [{'counter': 2, 'name': u'demoprogram'}]>

Now if you wanted to rename the duplicates, then you got two options here.

 1. Rename duplicate column using django orm
 2. Rename duplicate column using sql and django cursors

<br />
##### Method 1 : Rename duplicate column using django orm

One using the result above and feeding it back to django orm.

    duplicate_programs_obj = Program.objects.filter(program_name__in=[item['program_name'] for item in duplicate_programs])

This would give you a list that you can loop through and update the duplicate column to your liking

    for program in duplicate_programs_obj:
	    program.program_name = program.program_name + str(program.id)
	    program.save()
	    
<br />
##### Method 2 : Rename duplicate column using sql and django cursors
The other method involves using some raw queries and django cursors.

    from django.db import connection, transaction
    
    query = """
    UPDATE program T1 JOIN (SELECT program_name FROM program GROUP BY program_name HAVING count(id) > 1) dup ON T1.program_name = dup.program_name SET T1.program_name = CONCAT(T1.program_name, CAST(T1.id AS CHAR));
    """
    cursor = connection.cursor()
    cursor.execute(query)
