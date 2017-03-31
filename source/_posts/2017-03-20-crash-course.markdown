---
layout: post
title: "Crash Course DevOps"
date: 2017-03-20 11:12
comments: true
categories: DevOps
---

## Wires, cables and WiFi
  - Bits sent as light beams, no signal loss
    - faster than copper
  - WiFi is radio and then translated into physical bits over the wires
  - Bitrate -> bits per second -> how fast it can transmit
  - bandwidth -> how much data can you receive over a period of time
  - latency -> how long it takes, more hops to talk to Seiji than
  Kaitlin in the next room; ping time * distance

  - `traceroute` to see hops


## IP addresses and DNS
  - ISP
  - IP is a unique address
    - IPv4 - 4 billion unique addresses isn't enough
       - 32 bits, 8 octets
        - 32 bits long, 8 bits for each part of each address
       - DHCP -> obtaining a lease renewal process on your network.
        - to the outside world, Flatiron has the same IP provided
       by ISP
        - router provides guests with temporary IP depending on how long
        your lease renewal is set
       - renegotiate IP
       ?- subnet mask
       - 255.255.255.255 is the max it could go, based on the octet
       - static IP -> unique in the world
       - private IP -> re-use private IP addresses behind networks
   - IPv6 - 128 bits instead of 32
    - hex representation to prevent us running out of static IPs
    - DNS servers are split up in TLDs
      - DNS on a router

    - google's DNS will break it up by the TLD and domain
    - [google DNS](http://www.macworld.com/article/2824564/slow-internet-edit-your-dns-settings.html) versus open DNS
    - ?www doesn't mean anything any more, just another subdomain
    - ?CS of how the domain names at the DNS are stored?

   - TTL
     - this record will expire at X time
     - set TTL to an hour, it won't have to look it up for an hour
     - DNS propagation

  - DNS -> record type
    - A record -> address
    - maps the word name the domain to a physical IP address
    - PTR -> pointer -> the reverse, input IP and get the domain
    - FQDN -> A fully qualified domain name ([FQDN](http://stackoverflow.com/questions/19480767/domain-names-with-dots-at-the-end)) is the complete domain name for a specific computer, or host, on the Internet.
      - Host name is gmail and .com is the TLD
    - CNAME -> mail.google.com is a CNAME of googlemail.l.google.com.
      - A records should be unique
    - why is there a dot at the end?
      - it is an absolute as opposed to the relative address
    - want multiple MX records, redudency strategy


## Packet, routers and reliability
  - fault tolerant
  - TCP
  - ?How do they determine the route?
    - routers own the ISP and the companies that own them

  - traceroute domain.com
  - wireshark is a GUI of [`tcpdump`](https://danielmiessler.com/study/tcpdump/#gs.9p=ZVMQ)

  - IP address can change and it has a serial number or a MAC address
  (hardware address)

## HTTP & HTML
  - SSL and TLS (successor)
    - http listens on 80 and https listens on 443
    - sslv3 has been deprecated
  - certificate authority vouches for site
  - OpenSSL generates keys, authority will sign that
  - self-signed certs like for nagios or letsencrypt will work fine
  - SSLS
    - discrete logorithm problem
  - handshake process -> how to keep box locked and send secret
    - put treasure in box, lock box, send to friend
    - friend puts lock on box, sends it back
    - I remove lock from box and send back
    - friend unlocks box
  - SSH
    - ssh forwarding sends private key along
    - asymetric only used for authentication
    - symetric is then used for encryption and decryption
  - [bcrypt](https://en.wikipedia.org/wiki/Bcrypt) is what we use for email

## DDoS
- [DNS resolvers](https://en.wikipedia.org/wiki/Domain_Name_System#DNS_resolvers) to amplify attack


## DevinOps in review
  - [Octopus gem](https://github.com/thiagopradi/octopus) -> pooling, load balance select statements to read only
  replicas
  - DB sharding
    - complex SQL joins, will put different tables in different DBs
    - replication
  - floating IPs points to the master
    - static IP never changes
    - use floating IPs rather than DNS because of propogation
  - usernames:
    - if you have a server on linux it should not be running on root
    - if it's a system process then it would be ok to run on root
    - postgres is run as the postgres user
      - apache is run by deployer and passenger -> how ruby achieves
    paralellization (a module for apache)
    - deployer for Ironboard -> easy way to manage keys
    - how owns the process, who owns the directory where the config
    files lives
  - `etc/passwd` -> all the users on the box and who is logged in
  - every service that has a port open to the internet it should have
  its own user
  - username is usually the service name
  - `/var` is usually the log directory
  - `/etc` is usually the config directory
  - WAL-E
    - ship our binary logs we sent to s3
    - [write ahead logs](https://en.wikipedia.org/wiki/Write-ahead_logging) -> must be complete before actually modifies the
    DB with a transaction. This is the mechanism for rollbacks.
       - master just sends the write-ahead logs to the slave which then
      just replays them
  - Backups
    - take a base and then the have these WAL backups and send them off
    and it will apply all the deltas
    - can give us point in time restoration
    - these logs will fill up our disk
    - ? how long do we keep WAL-E
    - interface for deleting backups, s3 logs
    - config of pg is `pg_hba.conf`
    - script to switch over primary/replication script turns `recovery.conf` to `recovery.done`
    - `failover.sh` on the other replica as root
      - breaks replication, now need to configure replication on the new
      replication server
    - [iptables](https://en.wikipedia.org/wiki/Iptables) -> firewall

## Permissions
  - User, Group, World -> multiple users on the same machine, make sure
  processes don't do stuff they aren't supposed to
  - chmod 755, 644
  - all directories have to be 7
    - directories point to other files
  - cd is a program that takes a directory (file) as an argument and
  executes it
  - `etc/sudoers` -> determines who has root permissions; visudo -> creates a backup and prevents brackage
  - `useradd` give them a shell and name the user; want to add to the
  chef script

## load balancer
  - front-end is learn.co, terminating SSL, in the 
  - backend -> 
  - should be root on 

## Debugging
  - `passenger-status --show=requests`
  - `passenger-status`

## Automatic provisioning
  - [doctl](https://github.com/digitalocean/doctl)
  - [tugboat](https://github.com/petems/tugboat)

## cron
  - sends mail

## IDE backend
  - backend application -> IDE umbrella
  - main one is learn-ide-server cookbook
  - different chef servers
  - wombat
  - traffic cop
  - elixir-build01 -> build elixir on server because linux
  - new server needs to be added to [HAproxy](https://github.com/flatiron-labs/students-chef-repo/tree/master/cookbooks/learn-ide-haproxy)
  - lb -> `balance url_param token` hashing algorithm that determines
  which server the IDE connects to based on their Learn oauth token. (Optimization -> make hashing algo
  more granualar so that if a machine gets taken out the rotation, the
  othere aren't rebalanced as well
  - Load balance assignment is determined by dynect traffic management
    - own health monitoring
  - [gluster](https://www.gluster.org/) is fancy NFS
    - RAID -> redundant array of independent disks
  - [rkt](https://coreos.com/rkt/)
  - PTY - psuedoterminal, terminal emulator, connect to an arbitrary shell
  - inotify -> FS event watcher
  - containerization
    - [aufs](https://en.wikipedia.org/wiki/Aufs) loser -> [unionfs](https://en.wikipedia.org/wiki/UnionFS) winner that was merged into linux
  - ? do you bump archived tar'ed files when you archive again

## IDE Umbrella
  - for adding IDE server ([node list](https://github.com/flatiron-labs/ide_umbrella/blob/master/config/prod.exs))
  - dependencies in `mix.exs`; [cowboy](https://github.com/ninenines/cowboy) is the webserver, [poolboy](https://github.com/devinus/poolboy)
  - applications are like slightly fancy supervisors, [distillery](https://github.com/bitwalker/distillery) release packaging
  - `mix deps.get` -> get dependencies
  - `iex -S mix`
  - `:cowboy.start` -> erlang library, cowboy is lib which is an atom
  - `gen_server`, an abstraction on top of processes in general
    - provides state and a little behavior
  - `agent` is just for state
  - every connection gets its own process
  - distillery builds them
    - release -> full replacement of previous release, must restart
    - upgrade -> release plus upgrade instructions, relup file, modify
    the code in memory -> hotswap; preferable to release
    - `mix edeliver version qa`
    - `mix edeliver version production`
    - `mix edeliver build release`
    - `mix edeliver deployer release to qa`
    - `mix edeliver restart qa`
    - `bin/ide start`
    - `bin/ide attach` -> quit with ^D, not ^c (will kill process)
    - `bin/ide remote_console`
    - `mix edeliver build upgrade --with=0.1.0+232424323-hdhfd`
    - `mix edeliver deploy upgrade to qa` -> will prompt for version
    number

## Chef
  - server provisioning
    - consistency, automation
  - inheritance in the cookbooks, base cookbook -> security
  - like ruby base cookbooks
  - [wrapper cookbook](https://blog.chef.io/2013/12/03/doing-wrapper-cookbooks-right/), like forking a cookbook without modifying it
    - increasing levels of abstraction
  - conventions of chef aren't very clearly defined
  - differences between recipes and cookbooks?
