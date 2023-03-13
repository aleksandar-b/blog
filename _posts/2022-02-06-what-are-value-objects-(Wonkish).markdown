---
published: true
---

> "That which always is and has no becoming." -Plato

In this post I argue that value objects are programming language substitute for abstractions in natural languages where they appear as common nouns.

#### Values are _pure abstractions_
The main feature that distinquish value objects from entities is that values are pure abstractions(universals, concepts, plato's form). All differences between values and entities are derived from this ultimate distinction.

Bellow is a list of differences and the consequences they have.

#### Values are not instantiated
Concept of instance does not apply to values. Abstractions can be instatiated but at that point they become entity(particular thing). On conceptual level both your application entity classes and value classes are abstractions, with one difference that entity classes are instantiated while value classes always stay at the abstraction layer. It is remarkable that no one knows how keyword _new_ came into existence and what was it's purpose. Yet it is ubiquitous. In early OOP languages like Smalltalk and Simula objects/entities are created by explicit request (the _new_ operation), and are destroyed by a garbage-collector when no longer needed. So conceptually _it is not correct_ to use _new_ keyword for values.

![Abstractions/Values can not be instantiated](https://raw.githubusercontent.com/aleksandar-b/blog/gh-pages/_posts/carbon.png)

Removing new keyword reads like a functional programming in Typescript
![Abstractions/OOP without new](https://raw.githubusercontent.com/aleksandar-b/blog/gh-pages/_posts/carbon%20(1).png)

#### Concept of existence is not applicable to abstractions
Since they can't be instantiated, it is said that concept of existence is not applicable to abstractions. It is meaningless to speak about them as coming into existence or going out of the existence. When you write 2 + 3 = 5 there is no notion that 5 came into existence. No, it is timeless relation.

Let's look at typical example of value - number two. What exactly is number two?
Number two is an abstraction that subsumes all particular pairs of entitites out there. It subsumes pair of apples in your kitchen, pair chairs in your office, pair of shoes, two persons married. While all those particular entities may come and go out of the existence, what remains is the abstraction two. Since it never comes into existence and existence is only possible in time it is said that abstraction two is eternal or atemporal. To paraphrase Plato's distinction between being and becoming: Number two always is (being) but it does not (be)come into existence (and go out of existence) - it does not have lifecycle.

#### Abstractions don't change
Abstractions can have attributes like entities, but they don't change it's attributes. Changing it's attributes causes it to be different abstraction. This is because abstractions are common properties accross collection of phenomena. `Money(2, "$")` is different abstraction than `Money(10, "$")` because we are are not talking anymore about the same collection. In today's jargon we would say they are immutable. 

#### Abstractions don't have state
Since they can't be created and ergo they can't be changed it follows that they don't have state. State is defined as snapshot of properties of an entity at some particular time. We could also associate with Plato who said about forms that "they are always in the same state".

#### Abstractions can not be shared or copied, there is only one instance of it
In a expresion 1+1=2 it is meaningles to ask which number two did I change, as it is also meaningless to answer with: that number two or other one. There is only one number two.

#### Abstractions lack causal power
Since they can't be put into existence, they can't influence other entities or being influenced by them - they are outside of the causal order of the world. They can be just compared, related and measured.

#### Abstractions are common nouns
Natural languages distinquishes between common nouns and proper nouns. It is usefull heuristic which shows that programming languages should also distinquish those concepts.
Common nouns are generic things like country, while proper nouns are specific entities like Spain. Spain came into existence in some point in time and space, changed it's attributes through time, and will eventually go out of the existence.
