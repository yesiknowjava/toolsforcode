---
title: "Fastest Way to Setup Angular on Your Ubuntu Virtual Machine"
date: 2018-10-19T14:24:24+05:30
draft: false
categories: ["code"]
tags: ["e-learning"]
featuredImage: "img/code/fastest-way-to-setup-angular-on-your-ubuntu-virtual-machine.jpg"
Description: "step by step instruction on setting up angular on ubuntu virtual machine."
---

You have a shiny new virtual machine running Ubuntu 16 or 18 and you now want to be able to Install and Run Angular.

If you haven’t yet installed your Ubuntu VM, here is the article to first do the same.

I am not going to make this article verbose as I feel developers are restless when it comes to learning technology. So here it is .. the fastest way to install angular js on ubuntu

update your repositories

    sudo apt-get update

Install node

    sudo apt-get install nodejs

Now run this on the terminal.

    npm -v

If it doesn’t work, then do this

    sudo apt-get install npm

Check your node version by doing this

    node -v

Remember to install the latest version of node always and not the LTS version

Yaay, Node is installed

 

Install Nave
Nave is used to change between Node versions like so

    nave use 7.9.0

To do that we need to install

    npm install -g nave
 

Install Yarn Package Manager
Why use Yarn (a package manager from Facebook) when you can use npm (Node package manager). There are couple of advantages, you will not have dependency install issues with packages. Also, subsequent install of the same package in a different project will be faster as yarn will install it from the local repository instead of getting the same from the internet.

    npm install -g yarn
 

Install Angular using Yarn
    yarn global add @angular/cli

If you get errors from the same, do this with npm for one last time,

    npm install -g @angular/cli
 

Switching between package managers

Use yarn as packageManager

    ng config -g cli.packageManager yarn

Use npm as packageManager

    ng config -g cli.packageManager npm
 

Create an angular app
    sudo ng new awesomeangular
    cd awesomeangular
 