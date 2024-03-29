---
layout:     post
title:      Do Androids Dream of Electric Frogs?
date:       07-07-2015 11:00:00
summary:    Visualising neural network hallucinations with Google DeepDream.
categories: deeplearning
---

### Google DreamDream

[Google recently blogged](http://googleresearch.blogspot.co.uk/2015/06/inceptionism-going-deeper-into-neural.html)
about a visualisation tool called DeepDream they made for visualising
neural networks. Neural networks are often described as
[black boxes](http://stats.stackexchange.com/questions/93705/meaning-of-a-neural-network-as-a-black-box) -
although they can
[approximate any function](http://neuralnetworksanddeeplearning.com/chap4.html),
the structure of the network doesn't give insight to the structure of
the function being approximated. The
[original aim of the tool](http://googleresearch.blogspot.co.uk/2015/07/deepdream-code-example-for-visualizing.html)
was to help understand how neural networks carry out classification
tasks, but Google found the process can generate "beautiful" (terrifying) art.

### Hallucinations

The final product.

![alt text](/img/pepes/animated.gif "ILLUMINATI")

I supplied [this sad frog]/) to Google DeepDream via the ipython notebook
([instructions here](http://googleresearch.blogspot.co.uk/2015/07/deepdream-code-example-for-visualizing.html)). 
![alt text](/img/pepes/1.jpg "Pepe the melancholy frog") 

As the network tries to classify these sad frogs some patterns
emerge.
![alt text](/img/pepes/2.jpg "We must go deeper")

Portions of different species of bird begin to appear along with a car
and some legs.
![alt text](/img/pepes/3.jpg "We have delved too greedily")

In the last iterations the network classified dozens of eyes.
![alt text](/img/pepes/4.jpg "... and too deep")
