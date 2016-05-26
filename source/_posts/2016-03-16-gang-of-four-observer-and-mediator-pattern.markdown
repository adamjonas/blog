---
layout: post
title: "Gang of Four - Observer and Mediator Pattern"
date: 2016-03-16 13:32
comments: true
categories: books
---

## Observer

  - subject is a logical place to keep track of the collection of the observers
    - the upside is the observers needing to check with the subject via something like long-polling versus the subject notifying the owners
  - ActiveRecord before_actions and after_actions are a ruby implementation of the observer pattern
  - How does JS does this?
    - functions are first class object, easy to pass around

## Mediator

  - what's the difference between mediator and observer
    - Define an object that encapsulates how a set of objects interact.
    - Mediator is a little more specific, it avoids having classes communicate directly but instead through a mediator. This helps the Single Responsibility principle by allowing communication to be offloaded to a class that just handles that.
  - replaces many to many interactions with one to many interactions.
