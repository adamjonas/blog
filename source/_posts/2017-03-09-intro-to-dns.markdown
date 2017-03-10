---
layout: post
title: "Intro to DNS"
date: 2017-03-09 11:00
comments: true
categories: DNS
---

With Maarten Balliauw

  - people know should more about DNS and the http level

## DNS 101
  - How the internet works
    - IPv4 or IPv6
    - Check own operating system files to see if the host file has a
    record is known
    - will check the DNS cache for the local machine
    - OS will ask the router and check its own host file and DNS cache
    - same process for the ISP
    - the ISP will then go to the root server, address of the
    authoritative server
    - 6 hubs look ups

    - `nslookup google.com`
    - `dig A google.com +trace`

    - two types of servers
      - authorative (owns the domain)
      - cache (recursor) -> resolves the domain for you
    - DNS protcol designed in 1983
      - designed to map a domain name to an IP address
      - added TXT records and IPv6
    - TLD managed by separate organizatons (verisign, canadian internet
    registrartion authority)
      - all make their own rules e.g. need to be a canadian to be a .ca
      domain name, transfer rules
    - hierarchical system:
      - hit `.` first
      - then TLD like `org, com, ca`
      - can also create maps within a specific domain and could create
      own hierarchy like google does
    - caches
      - TTL -
      - cannot clear cache at ISP
      - keep the old IP address to maintain both

  - DNS zones
    - UDP protocol
    - only 13 root servers across the world
    - `root-servers.org`
    - $100k/yr to get own TLD
    - ? where does the money for those fees go for buying a TLD?

    - a text file and are hierarchical
    - SOA -> start of authority
    - Name of authoritive master name server (NA)

    - CNAME - redirect at the DNS record
    - MX - find mail server at specific address
    - TXT - validate domain ownership/spam rules
    - SRV - descibes a service type and port (like for in network
    printer)
    - PTR - reverse DNS

    - zone transfers
      - most IPs require more than 1 nameserver
      - master name server and that will sync with slave nameservers
      - no authentication and may expose internal services

## Security
  - old protocol
  - cache poisoning
  - DNSSEC - checks the origin - certificate chain
  - most modern browsers are checking for DNSSEC records

  - DDoS
    - lots of open resolvers out there
    - DNS amplication for DDos
    - disable recursion

## DNS in application archtecture
  - DNS failover and load balancing
  - add multiple DNS records -> will be a poor man's load balancer
  because it will return an random record
  - intelligence DNS server (CNS)
  - configuration in DNS
    - use DNS as a configuration store
    - DNS record could point to a TXT value
  - service discovery

## DNS for fun and profit
  - Abusing DNS
    - public hotspots
    - proxy server translating HTTP

  - iodine - same HTTP over DNS - tunnel traffic
    - `code.kryo.se/iodine`
