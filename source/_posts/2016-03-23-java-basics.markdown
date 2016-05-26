---
layout: post
title: "java basics"
date: 2016-03-23 13:49
comments: true
categories: java
---

## Some basics

  - Here's a basic method signature `public static void main(String args[])`
  - The void keyword allows us to create methods which do not return a value. Otherwise in java you need to specific what type the return value must be.
  - `public` is a Java keyword which declares a member's access as public. Public members are visible to all other classes. This means that any other class can access a public field or method. Further, other classes can modify public fields unless the field is declared as final.
    - A best practice is to give fields `private` access and reserve `public` access to only the set of methods and `final` fields that define the class' public constants. This helps with encapsulation and information hiding, since it allows you to change the implementation of a class without affecting the consumers who use only the public API of the class.

  - In Java, you need to have a method named `main()` in at least one class. This method must appear within a class, but it can be any class.

  - ints don't evaluate to `true`

## [interfaces](https://docs.oracle.com/javase/tutorial/java/concepts/interface.html)
  - An interface declaration consists of modifiers, the keyword interface, the interface name, a comma-separated list of parent interfaces (if any), and the interface body.
  - [Interface programming](https://en.wikipedia.org/wiki/Interface-based_programming) is an architectural pattern for implementing modular programming at the component level in an object-oriented programming language which does not have a module system.
  - Implementing an interface allows a class to become more formal about the behavior it promises to provide. Interfaces form a contract between the class and the outside world, and this contract is enforced at build time by the compiler. If your class claims to implement an interface, all methods defined by that interface must appear in its source code before the class will successfully compile.

  - **inheritance**
    - A java class cannot extend more than one class at a time so it won't provide support for multiple inheritance in classes, but it can extend more than one interface at a time so we java can support multiple inheritances with regard to interfaces.


## HAS-A relationship
  - HAS-A means an instance of one class "has a" reference to an instance of another class or another instance of same class.
  - It is also known as "composition" or "aggregation".
  - There is no specific keyword to implement HAS-A relationship but mostly we are depended upon "new" keyword.
  - Composition:
    - Without existence of container object, if there is no chance of existence of contained objects then container and contained objects are said to be strongly associated and this strong association is known as composition.
    - Eg: A "university" has several "departments". Without existence of "university" there is no chance for the "departments" to exist. Hence "university" and "departments" are strongly associated and this strong association is known as composition.

## IS-A Relationship:
  - This refers to inheritance or implementation.
  - Expressed using keyword "extends".
  - Main advantage is code reusability.


