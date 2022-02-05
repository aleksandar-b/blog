---
published: false
---
## Values are abstractions, entities are not

* By entities I mean the same thing as objects.

### Values are _pure abstractions_

#### Abstractions don't have an identity
Abstractions are defined by particular entities which they subsume. While particular entities are identifiable through space and time, abstractions don't have an identity. It is meaningles to ask which number 2 did I change in 1+1, as it is meaningless to answer that number 2 or other one. 

#### Abstractions are eternal
Being abstration number 2 subsumes all particular pairs out there. It subsumes pair of apples in your kitchen, that pair chairs in your office, pair of shoes, two persons married. While all those particular entities may come and go out of the existence, what remains is abstraction 2.

#### Abstractions can not be instantiated
Being eternal means that concept of space and time do not apply to them. Abstractions don't have lifycycle, they can't be created (come into existance) or destroyed (go out of the existance). Concept of instance is meaningless to abstractions. In early OOP languages like Smalltalk and Simula objects are created by explicit request (the _new_ operation), and are destroyed by a garbage-collector when no longer needed. So technically it is not correct to use new keyword for values.

```js
new Money(2, "$") ❌
```

```js
Money(2, "$") ✅
```

picture of typical OOP code vs values

Typical OOP ❌
```js
List<Text> sorted = new ListOf<>(
  new Sorted<>(
    new Split(
      new TextOf(
        new File("/tmp/names.txt")
      ),
      new TextOf("\\s+")
    )
  )
)
```
When keyword new is removed it reads like a functional programming.

OOP without new keyword ✅
```js
List<Text> sorted = ListOf<>(Sorted<>(Split(TextOf(File("/tmp/names.txt")),TextOf("\\s+"))))
```

#### Abstractions don't change
Abstractions can have attributes like entities, but they don't change it's attributes. Changing it's attributes causes it to be different abstraction. Money(2, "$") is different abstraction than Money(10, "$")


### Values are common nouns

