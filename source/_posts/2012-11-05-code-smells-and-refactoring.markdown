---
layout: post
title: "code smells and refactoring"
date: 2012-11-05 15:05
comments: true
categories: refactoring lecture_notes
---

decomposition and synthesis

- [Code smells](http://www.codinghorror.com/blog/2006/05/code-smells.html) Jeff Atwood.
- [Summary](http://www.cs.usfca.edu/~parrt/course/601/lectures/refactoring/refactoring.html)
- http://c2.com/cgi/wiki?RefactoringImprovingTheDesignOfExistingCode

- http://en.wikipedia.org/wiki/Code_refactoring
- [etymology of refactoring](http://martinfowler.com/bliki/EtymologyOfRefactoring.html)
  - The obvious answer comes from the notion of factoring in mathematics. You can take an expressions such as x^2 + 5x + 6 and factor it into (x+2)(x+3). By factoring it you can make a number of mathematical operations much easier. Obviously this is much the same as representing 18 as 2*3^2. 

improve internal structure, but don't change the external behavior

- list of refactors - slide 7 in <http://www.slideshare.net/MarcusDenker/refactoring-1921411>

- code is written once, but read many times.


[refactoring list from fowler](http://www.refactoring.com/catalog/index.html)


  - [Spaghetti Code](http://en.wikipedia.org/wiki/Spaghetti_code)
    - Spaghetti code is a pejorative term for source code that has a complex and tangled control structure. It is named such because program flow tends to look like a bowl of spaghetti, i.e. twisted and tangled.

  - Duplicated Code
  - long method
  - large class
  - long parameter list
  - temporary variable assigned more than once, but not a loop or collection

  - [extract method](http://www.refactoring.com/catalog/extractMethod.html)
    - push logic to the model -> conditional logic belongs in the model
    - we're going to push the nastiness down into the model. That way it can be tested and, so we can more easily change it in the future. 

  - when you refactor, the first test is always create tests

  - good quotes <http://www.slideshare.net/hominhchuc/refactoring-your-code-key-step-to-agility-presentation>

  Martin Fowler : "a change made to the internal structure of software to make it easier to understand and cheaper to modify without changing its observable behavior“.

  William C. Wake : "Refactoring is the art of safely improving the design of existing code“.

  The goal of refactoring is NOT to add new functionality.
  The goal is refactoring is to make code easier to maintain in the future.
  The process of refactoring involves the removal of duplication, the simplification of complex logic, and the clarification of unclear code.

  refactoring versus rewriting

  lego versus playdoh slide 9 <http://www.slideshare.net/NeilGreen1/the-roi-of-refactoring-lego-vs-playdoh>

  Everything I need to know about refactoring I learned in kindergarden

   “I'm not a great programmer; I'm just a good programmer with great habits.”- Kent Beck

###Law of demeter?
  Get into this?
   
###E.g.s
- Inline class- <http://www.refactoring.com/catalog/inlineClass.html>
- Decompost conditional-  <http://www.refactoring.com/catalog/decomposeConditional.html>
- Extract Class - <http://www.refactoring.com/catalog/extractClass.html>
- Inline Method
- Replace Conditional with Polymorphism
- Replace Parameter with Method

- God class

<http://www.refactoring.com/catalog/>

###Code smells
<http://en.wikipedia.org/wiki/Code_smell>

extraction pattern- anti-pattern:
<http://blog.jayfields.com/2007/04/ruby-anti-pattern-extract-module-to.html>

Refactoring:
Even noobs know that refactoring is important. This presentation, inspired by <em>Refactoring: Ruby Edition</em>, will cover the whys, whens, and hows of refactoring using examples.