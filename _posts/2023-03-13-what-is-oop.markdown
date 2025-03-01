---
published: true
layout: post
title: What is Object oriented programming - once and for all.
category: posts
---
### Programming is simulation

What distinquishes OOP from other programming paradigms? For example - what distinquishes OOP from Functional programming?

I would like to talk about forgotten definition of early OOP which viewed that all programming is simulation. It was forgotten in 80s and early 90s when academics entered the field and in their desperate need to categorise everything tried to categorise OOP also. Certainly not all problems in programming require simulaiton approach - just some. For non complex tasks like data transformations, calculations, CRUD etc you can use Functional programming. What is common to all these non complex task is that they lack TIME component. But what exactly do we mean when we say that? I will try to answer bellow - it is not exactly time but something that is only possible through time.  

You certainly know, or had to memorise this dry academic categorisation of OOP:

1. Encapsulation
2. Polymorphism
3. Inheritance
4. Abstraction

I would like to restate the view from early 80s when OOP viewed the programming as simulation. It was influenced by Simula btw. 

What are objects? In real world we have objects and in programming we have objects. OOP was created to simulate some real world objects.

What it means to simulate? Let's have a look at description of Uncle Bob Martin about how OOP was created. At one moment he was very close to find what exactly is specific difference between OOP and other paradigms, but then he went on with typical encapsulation, polymorphism etc..

>OBJECT-ORIENTED PROGRAMMING
>The second paradigm to be adopted was actually discovered two years earlier, in 1966,
>by Ole Johan Dahl and Kristen Nygaard. These two programmers noticed that the
>function call stack frame in the ALGOL language could be moved to a heap, thereby
>allowing local variables declared by a function to exist long after the function returned.
>The function became a constructor for a class, the local variables became instance
>variables, and the nested functions became methods. This led inevitably to the discovery
>of polymorphism through the disciplined use of function pointers

Do you see what is the key part here? I will tell you - that part is "**exist** *long after the function returned*.". This was breakthrough. It means that objects can **live**, to have **existence**. In another words - you created simulation. To exists or to live means that passage of time does not anihiliate concrete identifieable object. Existence is only possible in time, even just for a split of a second. Existence has a lifecycle - something can come into existence, go out of existence and be changed during existence (state), while biggest changes being coming and going out of existence. Something that does not come into existence but can be defined is considered eternal or atemporal like abstractions. For example number two. Functional programming is all about abstractions that don't come into existence and don't change it's properties or states. But you can not build anything usefull this way, you are just doing math. Complex aplication are complex because they try to simulate some part of real world.

So we see that Simulation has some parts that should be defined:

1. Existence (only possible in Time)
2. Objects (identifieable things)
3. Change - Objects interact with each other (they act on some other objects or are being acted upon)

Those 3 things can not exist without each other.
Objects require existence so they can live, otherwise they would be blury abstractions.
But to exist is to have causal power or ability to change something or being changed by something.
And there is no time or existence without some change.