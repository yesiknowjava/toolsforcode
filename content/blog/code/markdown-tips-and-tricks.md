---
title: "Markdown tips and tricks"
date: 2024-03-09T19:43:28+05:30
draft: false
image: "images/post/post-2.png"
categories: ["code"]
tags: ["markdown"]
---

## How to create an empty paragraph or Blank New Line in Markdown {.className class="h5"}

There are many ways to create an empty paragraph or Blank New Line in Markdown

### RAW {.className class="h6"}

Using the non-breaking space ASCII character
```&nbsp;```

### HTML {.className class="h6"}
Using the ```<br />``` tag

### HTML Entity {.className class="h6"}
Using the HTML entity ```&NewLine;```

### Backticks with a space inside followed by two spaces {.className class="h6"}
`backtick (space) backtick (space)(space)`


## How to set attributes like class, id to some elements in Goldmark Markdown processor. {.className class="h5"}

To set the id, class and custom attribute to a heading tag use the below example 

```heading {#id .className attrName=attrValue class="class1 class2"}```

This would generate the following html

```<h3 id="id" class="className class1 class2" attrname="attrValue">heading</h3>```





