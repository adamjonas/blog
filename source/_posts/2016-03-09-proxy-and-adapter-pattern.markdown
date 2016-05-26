---
layout: post
title: "Gang of Four: Proxy and adapter pattern"
date: 2016-03-09 13:10
comments: true
categories: books
---

## Proxy

  - reverse proxies
  - virtual proxy: creates expensive objects on demand. the worker box maybe?
    - infinite scroll or pagination (these objects exist in Octokit, where there are objects as placeholders but it hasn't acutally fetched the data)
    - memoization example in the ruby boook
    - [collection proxy](http://edgeapi.rubyonrails.org/classes/ActiveRecord/Associations/CollectionProxy.html)

## Adapter (aka wrapper) 

  - Fog: cloud storage
  - ActiveRecord
  - OctokitWrapper is more of a decorator because it adds additional implementation on top of Octokit
  - Gateway pattern is an adapter specifically created to talk to external services
  - HierarchyBuilder is the adapter
  - The key difference between bridge and apater lies in their intents.
    - Adapter focuses on resolving incompatibilities between two existing interfaces. Bridge, on the other hand, bridges an abstraction and its (potentially numerous) implementations.
