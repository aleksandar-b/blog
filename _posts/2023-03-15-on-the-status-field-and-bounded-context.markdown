---
published: true
layout: post
title: On the Status field
category: posts
---

I want to talk about new code smell - I want to name it as multiple substatuses code smell. Based on this I also want to propose a new practical solution for decomposing bounded context.

You know that God classes that always have `status` or `state` field but also one or several more "subStatuses" like `paymentStatus`, `shippingStatus`, `submissionStatus`.

```js
class Ticket {
    id: string;
    customerId: string;
    `status`: string;
    ...
    `shippingStatus`: string;
    shippingAddress: string;
    `paymentStatus`: string;
    paymentId: string;
    `submissionStatus`: string;
    submissionId: string;
    ...
}
```

This is a code smell ***multiple substatuses*** and it is a clear sign that you are dealing here with ***multiple bounded contexts*** which are all tightly coupled into this god class. Decomposing bounded context is more of an art then science and there is no clear way how to do that. There are "heuristics" that can help you with that process like:

- Different vocabulary
- Different teams
- Different policy
- Different business goal
....etc

I want to propose this new practical solution to decomposing new bounded context: look at the ***multiple substatuses***. If it has more that one status field then it is a sign that ***each substatus should be in different bounded context***  with it's own complex process, workflow etc. You thus place it into it's own microservice to encapsulate change and allow independent deployability. Status field is very important when looking from outside, it is end result of some complex process that runs inside of that context.

Our God class should be decomposed into several microservices: Shipping, Finance, Submission.
```java
class Ticket {
    id: string;
    customerId: string;
    ...
    status: string;
    
    // Shipping context
    shippingStatus: string;
    shippingAddress: string;
    
    // Finance context
    paymentStatus: string;
    paymentId: string;

    // Submission context
    submissionStatus: string;
    submissionId: string;
    ...
}
```

Each new class inside of microservice should have a loose reference to ticket with ticketId.

```java
// Finance microservice
class Payment {
    id: string;
    ticketId: string;
    status: string;
}
```


```java
// Shipping microservice
class Shipment {
    id: string;
    ticketId: string;
    status: string;
    address: string
}
```


```java
// Submission microservice
class Submission {
    id: string;
    ticketId: string;
    status: string;
    externalId: string
}
```

Ofcourse, for a view model where you serve json to frontend for display purposes it is allowed to have multiple substatuses where data is retreived and composed from multiple microservices via API Gateway. General rule is that you almost never want a database table which has several substatuses.