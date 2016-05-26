---
layout: post
title: "Growing Object-Oriented Software, Guided By Tests"
date: 2016-05-28 16:51
comments: true
categories: books notes
---

## Object-Oriented Style

> We value code that is easy to maintain over code that is easy to write. Implementing a feature in the most direct way can damage the maintainability of the system, for example by making the code difficult to understand or by introducing hidden dependencies between components. Balancing immediate and longer-term concerns is often tricky, but we’ve seen too many teams that can no longer deliver because their system is too brittle. p. 47

>Encapsulation and Information Hiding
  We want to be careful with the distinction between "encapsulation" and "information
hiding." The terms are often used interchangeably but actually refer to two separate,
and largely orthogonal, qualities:
  Encapsulation
  Ensures that the behavior of an object can only be affected through its API.It lets us control how much a change to one object will impact other parts of the system by ensuring that there are no unexpected dependencies between
unrelated components.

  Information hiding
  Conceals how an object implements its functionality behind the abstraction of its API. It lets us work with higher abstractions by ignoring lower-level details that are unrelated to the task at hand. p. 49


> Our heuristic is that we should be able to describe what an object does without using any conjunctions (“and,” “or”). If we find ourselves adding clauses to the description, then the object probably should be broken up into collaborating objects, usually one for each clause. p. 52

Context Independence
> While the “composite simpler than the sum of its parts” rule helps us decide whether an object hides enough information, the “context independence” rule helps us decide whether an object hides too much or hides the wrong information. p.54

## Achieving Object-Oriented Design

> Interface and Protocol
Steve heard this useful distinction in a conference talk: an interface describes whether two components will fit together, while a protocol describes whether they **will work** together. p. 58

> Kernighan and Plauger attribute the idea of pipes to Douglas McIlroy, who wrote a memo in 1964 suggesting the metaphor of data passing through a segmented garden hose. It’s currently available at [http://plan9.bell-labs.com/who/dmr/mdmpipe.pdf](ttp://plan9.bell-labs.com/who/dmr/mdmpipe.pdf). p. 66

## The Sniper Makes a Bid

> Defer Decisions
There’s a technique we’ve used a couple of times now, which is to introduce a null implementation of a method (or even a type) to get us through the next step. This helps us focus on the immediate task without getting dragged into thinking about the next significant chunk of functionality. The null Auction, for example, allowed us to plug in a new relationship we’d discovered in a unit test without getting pulled into messaging issues. That, in turn, meant we could stop and think about the dependencies between our objects without the pressure of having a broken compilation. p. 136

> **When the facts change, I change my mind. What do you do, sir?**
  —John Maynard Keynes p. 172

