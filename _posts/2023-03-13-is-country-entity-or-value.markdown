---
published: true
layout: post
title: Is Country an Entity or Value object?
category: posts
---

Let's explore some edge case where you have a Country class that serves only as a value to some other entity.

```js
class Country {
    id: string
    name: string
}
```

Do you think this should be a value or an entity? 

It depends on a context of your application of course but it also depends how you define entity.

Most of programmers define Entity as everything that can be identifiable. Usually it has some id. So in this case it is Entity.

Some add that it must have lifecycle. In this case it is value.

I would like to add 3rd distinction - Causal power.

Something has causal power if it has capacity to do something or have something done to it.

Or in simpler terms:

> Ability to act upon something or being acted upon.

So if Country class is value if it does not have direct or indirect methods to change some entity or being changed by them.

Direct:
1. Is not changed by some other entity via method calls
2. Does not change other entity via method calls

Indirect:
1. Does not listen to events
2. Does not dispatch any event by itself

When you create a simulation/program you created live enitites that interact with each other. To live is to have causal power. The whole world is interaction. If something has an ID but it does not participate in causal order of the world it is the same as if it does not exist - it is just dead abstraction.

