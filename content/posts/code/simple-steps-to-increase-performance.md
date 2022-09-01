---
title: "Simple steps to increase the performance of a web application."
date: 2019-11-02T14:24:24+05:30
draft: false
categories: ["code"]
tags: ["e-learning"]
featuredImage: "img/code/server.jpg"
Description: "Simple steps to increase the performance of a web application."
---

Lets say you are tasked to analyze and increase the performance of a website. What are the things you would look into. What would you improve or what would you avoid.

This brief article discusses the simple steps to increase the performance of a web application.

### Performace considerations

There are 3 places where performance can be increased

1. 1. Network Level
2. 2. Server Level
3. 3. Database Level
4. 4. Application Level
  
<p></p>

#### Network Level
At network level we can do the following optimizations.

1. 1. Reduce Number of requests, by combining requests
2. 2. Use CDN's like cloudflare, maxcdn, cloudfront etc
3. 3. Minifiying the html, css and js content before sending it to the client.
4. 4. Use Local Caching to store data in the client browser using techniques like localstorage and sessionstorage

<p></p>

#### Server Level
At server level we can do the following optimizations.
<p></p>

1. 1. horizondal scaling - increase number of servers and put them after a load balancer.
1. 2. vertical scaling - increase the hardware of the single server by buying s bigger machine

<p></p>
Advantage of horizondal scaling is there is no limit to the number of servers you can have. But a horizondal scaling cannot buy more than a supercomputer.
    
<p></p>


#### Database Level
At the database level we can use sharding (splitting) of data

#### Application Level

This is a very big topic in itself, but the keywords to look out are, optimized way of storaging data, asyncronous operations.




