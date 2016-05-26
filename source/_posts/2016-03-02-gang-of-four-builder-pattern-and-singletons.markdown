---
layout: post
title: "Gang of Four: Builder pattern and Singletons"
date: 2016-03-02 12:07
comments: true
categories: books
---

## Builder

  - Concrete builders: `html to markdown` and `html to json`?
  - Could we think of a complex cart like this? Like line items of a educational program might compose a composite object by the cart which is the director.
    - doesn't quite match up with subbing in different builders
  - like strategy pattern, but the way it differs is that it creates a composite object at the end
  - but this book is more about the abstract factory, the way this differs is that it the director gives you finer control of the order.
  - separating out **how** the object is built

  - e.g. Creating enrollments with one time purchases vs recurring subscriptions
    - client == browser
    - director == model ShoppingCart
    - builder1 == JobGuaranteeSubscription
    - builder2 == NonJobGuaranteeSubscription
    - result == subscription

    - Build part: slack group, google group, batch

## Singleton

  - there is only one instance and so if another part of the code changes it, then you will have shot yourself in the foot
  - publishers, which are all singletons, don't need more than one, but they could have been classes instead
  - dependency injection makes tests way easier
