---
published: true
layout: post
title: On the Status field
category: posts
---

I want to talk about new code smell - I want to name it as multiple substatuses code smell. Based on this I also want to propose a new practical solution for decomposing bounded context.

You may have come across so-called "God classes" in your code, which typically have a status or state field along with several other "subStatuses" like `paymentStatus`, `shippingStatus`, `submissionStatus`.

```js
class Ticket {
    id: string;
    customerId: string;
    `status: string;`
    ...
    `shippingStatus: string;`
    shippingAddress: string;
    `paymentStatus: string;`
    paymentId: string;
    `submissionStatus: string;`
    submissionId: string;
    ...
}
```

This is a code smell ***multiple substatuses*** and it is a clear sign that you are dealing here with ***multiple bounded contexts*** or "subjects" which have their own view of same object (perspective, dimension, ). Decomposing them is more of an art then science and there is no clear way how to do that. There are "heuristics" that can help you with that process like:

- Different vocabulary
- Different teams
- Different policy
- Different business goal
....etc

I want to propose this new practical solution for decomposing bounded contexts based on the presence of multiple substatuses. If a class has more than one status field, it is a sign that each substatus should be part of a different bounded context, complete with its own processes and workflows. You can then encapsulate these contexts within their own microservices, allowing for independent deployability and easier management. Status field is very important when looking from outside, it is end result of some complex process that runs inside of that context.

Our God class should be decomposed into several microservices: Delivery, Finance, Lodgement.
```java
class Ticket {
    id: string;
    customerId: string;
    ...
    status: string;
    
    // Delivery context
    shippingStatus: string;
    shippingAddress: string;
    
    // Finance context
    paymentStatus: string;
    paymentId: string;

    // Lodgement context
    submissionStatus: string;
    submissionId: string;
    ...
}
```

Each new class inside of microservice should have a loose reference to ticket with ticketId.

Finance microservice
```java
class Payment {
    id: string;
    ticketId: string;
    status: string;
}
```



Delivery microservice

```java
class Shipment {
    id: string;
    ticketId: string;
    status: string;
    address: string
}
```



Lodgement microservice

```java 
class Submission {
    id: string;
    ticketId: string;
    status: string;
    externalId: string
}
```

It's worth noting that, for view models where you serve JSON to the frontend for display purposes, it is acceptable to have multiple substatuses. In such cases, data can be retrieved and composed from multiple microservices through an API Gateway. However, as a general rule, you should avoid having multiple substatuses in a single database table.

By following this practical approach to decomposing bounded contexts, you can improve the maintainability and scalability of your code while reducing the risk of tightly coupled components.