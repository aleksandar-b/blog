---
published: true
layout: post
title: Don't instantiate value objects
category: posts
---

Values = Abstractions

#### Values are not instantiated

The main thing that distinquish value objects from entities is that values are _pure_ abstractions. Oposite of abstraction is a concrete thing (this or that). Something that can be identifieable by pointing finger to it.

![Abstractions/Values](https://raw.githubusercontent.com/aleksandar-b/blog/gh-pages/_posts/table_abstract.png)
The act of transitioning from abstraction to concrete is called instantiation.

Ergo, concept of instance does not apply to values. Abstractions can be instatiated but at that point they become entity(particular thing). And entity has an identity.

In real world we instantiate by identifying concrete thing we are talking about. How we identify? With time and space. I know you are not same as me because you are at location in space at this point in time than I am. There is also contextual identification like when I say "My aunt". Everyone can identify the person based on context. 

In programming we first used memory location to identify objects. Now we use GUIDs.

On conceptual level both your application entity classes and value classes are abstractions, with one difference that entity classes are instantiated while value classes always stay at the abstraction layer. 
It is remarkable that no one knows how keyword _new_ came into existence and what was it's purpose. Yet it is ubiquitous. In early OOP languages like Smalltalk and Simula objects/entities are created by explicit request (the _new_ operation), and are destroyed by a garbage-collector when no longer needed. _new_ keyword was a command that says to computer - put this thing into existence. So conceptually **it is not correct** to use _new_ keyword for values.

![Abstractions/Values can not be instantiated](https://raw.githubusercontent.com/aleksandar-b/blog/gh-pages/_posts/carbon.png)