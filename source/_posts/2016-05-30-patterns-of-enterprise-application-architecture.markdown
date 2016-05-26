---
layout: post
title: "Patterns of Enterprise Application Architecture"
date: 2016-05-30 17:08
comments: true
categories: books notes
---

## Introduction:

> “Architecture” is a term that lots of people try to define, with little agree- ment. There are two common elements: One is the highest-level breakdown of a system into its parts; the other, decisions that are hard to change. It’s also increasingly realized that there isn’t just one way to state a system’s architec- ture; rather, there are multiple architectures in a system, and the view of what is architecturally significant is one that can change over a system’s lifetime. p. 1.

> The subjectivity comes in here as well because, if you find that something is easier to change than you once thought, then it’s no longer architectural. In the end architecture boils down to the important stuff—whatever that is. p. 2

> *Responsiveness* is about how quickly the system acknowledges a request as opposed to processing it. This is important in many systems because users may become frustrated if a system has low responsiveness, even if its response time is good. If your system waits during the whole request, then your responsiveness and response time are the same. However, if you indicate that you’ve received the request before you complete, then your responsiveness is better. Providing a progress bar during a file copy improves the responsiveness of your user inter- face, even though it doesn’t improve response time. p. 7

### Patterns

> There’s no generally accepted definition of a pattern, but perhaps the best place to start is Christopher Alexander, an inspiration for many pattern enthusi- asts: “Each pattern describes a problem which occurs over and over again in our environment, and then describes the core of the solution to that problem, in such a way that you can use this solution a million times over, without ever doing it the same way twice” [Alexander et al.]. Alexander is an architect, so he was talking about buildings, but the definition works pretty nicely for software as well. The focus of the pattern is a particular solution, one that’s both com- mon and effective in dealing with one or more recurring problems. Another way of looking at it is that a pattern is a chunk of advice and the art of creating patterns is to divide up many pieces of advice into relatively independent chunks so that you can refer to them and discuss them more or less separately. p. 9


## Making a choice
