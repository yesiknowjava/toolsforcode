---
title: "Hugo Tutorial for Beginners"
date: 2018-11-21T00:09:02+05:30
draft: false
categories: 
    - code
tags: ["Static Site Generators"]
featuredImage: "img/code/hugo-tutorial-for-beginners.jpg"
Description: "This tutorial explores the basics of installing hugo on windows and ubuntu. It also shows how to create and run a simple site in hugo along with installing a custom theme"
---
Welcome to a short but enriching tutorial on hugo. I assume you have come to learn about hugo after understanding what hugo is. But for setting the ground lets start off by learning what is hugo.

Hugo is an SSG, short for Static Site Generator. Well what is a static site generator then. It is a tool that generates static html content from say markdown files. Why do we need it? Well its difficult to hard code each html page separately, thats why. But can't we use CMS's like wordpress for that? You can, but that would be an overkill for a simple blog or portfolio website. Moreover there are other benefits to hosting a static site over traditional CMS's. For one, static sites are secure. There is nothing to hack. No DB, no Nothing. Then there is speed. Since there is no calculations to make before serving the page, a web server is not required. Hence making it superfast. Also there is an added advantage of being able to host your website for lot less.

There are many SSG's out there that are really great. Take for example, Jekyll. To be honest Jekyll is more famous than Hugo. But Hugo does have some advantages of its own. Hugo is advertised as "The world’s fastest framework for building websites".


So lets begin learning without getting into which SSG's are the best. Below is a list of things that you will be learning in this "hugo tutorials for beginners" article

1. Install Hugo on Windows and Linux
2. Create a new hugo site
3. Download and install a theme from official hugo theme web page.
4. View the hugo site locally
5. Generate a Static Website that you can deploy anywhere.

<br />
### Install Hugo on Windows
Installing hugo on windows is quite easy. They provide an executable that you can download from [here](https://github.com/gohugoio/hugo/releases). Once you are there, find the download link for windows. You will have two versions for windows. A 32 bit and a 64 bit zip. Download whats appropriate for yours.

Now head over to your C: drive and create a folder called "Hugo". Note that the word Hugo has a capital H. It needs to be like that.

Then under the "Hugo" folder create another folder called "bin".

Now extract the zip file that you downloaded earlier and copy the contents of the zip contents inside the bin folder.

<br />
### Install Hugo on Ubuntu

Installing on ubuntu is quite straight forward

sudo apt-get install hugo
**Note** : Rest of the tutorial assumes you are working on windows, although from here it doesn't matter as all commands we are going to use are not operating system specific.

<br />
### Create a new hugo site

hugo new site YourSiteName
Hugo creates a new folder by the name "YourSiteName". If you look into the folder you will see few folders already created for you. Content folder is where your site contents, that is yours posts lives. Static folder will have your sites static files like css, js and images. Themes folder is where you can install or create themes for your new Hugo Site. config.toml is the main configuration file.

![](assets/20211113_105754_amenagement-512.jpg)

<br />
### Download and install a theme from official hugo theme web page.
Get inside the themes folder explained above. Now this folder will be empty as Hugo does not ship with any pre-selected theme like in wordpress. This is intentional and you can either install all of their themes or just the one you like. Installing a theme is quite easy too. You can clone the repository of the theme or download the zip file of the them and put the extracted theme folder under the themes directory. Hugo themes can be found [here](https://themes.gohugo.io/). And we are going to download [this](https://themes.gohugo.io/aerial/) one for the sake of this tutorial.

git clone https://github.com/sethmacleod/aerial.git
Now your theme is downloaded and to use it. You need to tell hugo that you are going to use this theme. You tell this by taking the name of the folder of the theme and entering it config.toml explained earlier.

In config.toml, enter the following line

theme = aerial
Note the name varies based on the name of the theme.

<br />
### View the hugo site locally
Now head over to your sites root directory and then type the command

hugo server
If no errors come at this stage, your site is ready and Hugo will run a development server at ***localhost:1313*** for you. Fire up a browser of your choice and open the above URL. You will see your website up and running there.

**Additional Info** : Most themes provide a folder called exampleSite. This contains some random posts and static files, to give you an idea of how the site will look like with content. To do this, you need to copy the contents of exampleSite and put it inside the root of your site

*Example*:

Copy the contents of

`C:\Hugo\YourSiteName\themes\ThemeName\exampleSite\`

and paste it to

`C:\Hugo\YourSiteName\`

<br />
### Generate a Static Website that you can deploy anywhere.

Once you are happy with your site you would want to deploy it some place. We will cover separate tutorials for that, but in essence you would need a folder full of html and static files. In order to get that, stop the dev server by pressing command + c in your terminal.

Now just type the command

hugo
Yes, just 'hugo'. Now hugo does some checks and creates a folder called public inside the root directory of your site. The 'public' folder contains all the folder needed to host the page statically.

In our next tutorial we will learn some advanced stuff.

More tutorials coming soon....
