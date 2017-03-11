---
layout: post
title: "Elastic Search"
date: 2017-03-10 11:38
comments: true
categories: search
---

## Intro
"elastic search is full text sreach engine, non-relational DB, analytics engine"

  - has clustering and managed over REST
  - Suggest Explicit mapping

  - keywords -> non-analyzed data
  - full text -> analyzed

  - filters -> will need `bool` then `filters`

## relevance -> score meta data field for document match
  - things are ranked
  - filters are faster and don't have relevance (so if you don't care, go with fiters)
  - can boost relevance

## multi-index multi-type
  - lots of power

## Aggregation -> group by on steroids
  - SQL: group by the bucket
  - aggregator -> can do nested group by and data retrieval

## Managing elastic search
  - clustering
    - odd number of nodes bigger than 1
      - 3 shards and replication
      - a third node can shuffle the shards and the replicas

## ELK Stack
  - elastic search, logstash, and kubana
  - logstash
    - want to parse and stash log data
  - kubana
    - front end visualizer
  - now beats added -> lightweight, written in go -> for shipping
