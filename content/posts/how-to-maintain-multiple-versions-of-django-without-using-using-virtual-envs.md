+++
title = "How to maintain multiple versions of django without using using virtual envs."
description = "Installing and running django version 1.x and django version 2.x in the same machine without using virtual env"
image = "/img/webhosting2.jpg"
featuredImage = "/img/webhosting2.jpg"
tags = ["code"]
categories = ["code"]
date = 2019-09-03T12:50:09.512Z
draft = false
+++
Most linux come installed with python 2.7. Some even come installed with both 2.7 and 3 as well.

django upto version 1.11 will work with python 2.7. Anything greater than that needs python 3.

If in a system you have both version of python each accessed by the terms python referring to 2.7 and python3 referring to version 3 and you want to run django 1.11 and django 2.2, how do we do that.

#### Creating django 1.11 project

```
python -m django startproject djangousing1point11
```

#### Running the project

```
python manage.py runserver
```

#### Creating django 2 project

```
python3 -m django startproject djangousing3
```

#### Running the project

```
python3 manage.py runserver
```
