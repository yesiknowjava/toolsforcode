+++
title = "How to convert po files into csv files"
description = "This article explains how to use a tool called python translate toolkit to convert an existing po file into a csv file."
image = "/img/translate-toolkit.jpg"
tags = ["python", "tools", "csv"]
categories = ["code"]
date = 2019-06-01T08:56:24.235Z
draft = false
+++
In my day job I work as a django developer, I once had to convert the translation files which are of the format '.po'

I was on the verge of writing a script to seperate the 'msgid' and 'msgstr' and put them as columns of the csv.

Suddently, it went through my mind that, 'it is not right to re-invent the wheel'. I started searching and I got this awesome python tool called the "Python Translate Toolkit".

It does so many things so very nicely. Installation is simple. You can either do this

`sudo apt install translate-toolkit` 

or you can download the python translate toolkit

`git clone https://github.com/translate/translate.git`

and then extract the files and do this within the extracted folder

`./setup.py install`

You get variety of tools with this simple installation

1. Converters: like csv2po, html2po etc
2. Tools (Quality Assurance):like pomerge, pofilter etc
3. Other Tools like pocompile, poswap

In my case, I wanted to convert my django po file into csv file and here it goes

`po2csv djangojs.po djangojs.csv`

Thats all for now.

For a full list go this web [site](http://docs.translatehouse.org/projects/translate-toolkit/en/stable-1.13.0/index.html)
