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

## Split Brain issue
  - [HOW TO AVOID THE SPLIT-BRAIN PROBLEM IN ELASTICSEARCH](http://blog.trifork.com/2013/10/24/how-to-avoid-the-split-brain-problem-in-elasticsearch/)

## Tinc
  - VPN -> encrypts traffic between servers

## Setting up elastic search
  - [setting up a elasticsearch cluster on ubuntu](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-elasticsearch-on-ubuntu-16-04)
  - used a ruby case statement to set the master versus the replicas up
  - [shards, replicas, documents explained](https://www.elastic.co/guide/en/elasticsearch/reference/current/_basic_concepts.html)
  - [Thoughts on Launching and Scaling Elasticsearch](https://qbox.io/blog/launching-and-scaling-elasticsearch)
  - [optimizing sharding](https://qbox.io/blog/optimizing-elasticsearch-how-many-shards-per-index)
    - `A good launch point for capacity planning is to allocate shards with a factor of 1.5 to 3 times the number of nodes in your initial configuration. If you're starting with 3 nodes, then we recommend that you specify at most 3 x 3 = 9 shards.`
    - `We reiterate that shards consume resources and require processing overhead.`
  - needed to bump vm.max_map_count according to [these instructions](https://www.elastic.co/guide/en/elasticsearch/reference/current/vm-max-map-count.html)
  - [UFW](https://www.digitalocean.com/community/tutorials/how-to-set-up-a-firewall-with-ufw-on-ubuntu-16-04) -> wasn't needed in the end
