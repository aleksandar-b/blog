---
published: true
layout: post
title: On the Status field
category: posts
---

You noticed that in whichever codebase you are working there is that status or state field in some class or table which is very important but causes lots of complexity? You start to work for another company and there it is again. It is so ubiquitous you start to wonder why languages are not threating it as first class citizen?

I want to talk about new code smell - I would name it as SubStatuses code smell. Based on this I also want to propose a new practical heuristic for decomposing bounded contex.

You know that god classes that have `status` field but also one or several more "subStatuses" like `paymentStatus`, `shippingStatus`, `submissionStatus`. 


```ts
class Ticket {
    id: string;
    customerId: string;
    ...
    status: string;
    shippingStatus: string;
    shippingAddress: string
    paymentStatus: string;
    paymentId: string;
    submissionStatus: string;
    submissionId: string;
    ...
}
```

This is a code smell `SubStatuses` and it is a clear sign that you are dealing here with ***multiple bounded contexts*** which are all coupled in this god class. Decomposing bounded context is more of an art then science and there is no clear way how to do that. There are "heuristics" like that can help you in that process like:

1. Different vocabulary
2. Different teams
3. Different policy
4. Different business goal

I want to propose this practical solution to decomposing new bounded context: look at the "subStatuses". If it has more that one status field then it is a sign that it should be in different bounded context with it's own complex process, workflow etc. It should be put into it's own microservice to encapsulate change and allow independent deployability. 


Our god class should be decomposed into several microservices: Shipping, Finance, Submission.
```ts
class Ticket {
    id: string;
    customerId: string;
    ...
    status: string;
    
    <Shipping context>
    shippingStatus: string;
    shippingAddress: string;
    
    <Finance context>
    paymentStatus: string;
    paymentId: string;

    <Submission context>
    submissionStatus: string;
    submissionId: string;
    ...
}
```

Each new class inside of microservice should have a loose reference to ticket with ticketId.