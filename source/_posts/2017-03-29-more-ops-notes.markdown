---
layout: post
title: "More Ops Notes"
date: 2017-03-29 16:18
comments: true
categories: DevOps
---

## Network partitioning causing exchange issues on rabbitmq
  - this was after netowrk maintenance
  - solution was to delete exchange which then is automatically added
  back [documented here](https://github.com/rabbitmq/rabbitmq-server/issues/887#issuecomment-290177962)

## Ubuntu 16
  - ubuntu 16 doesn't ship with upstart so sysctld is what we'll use to
  control services. [systemctl commands](https://www.digitalocean.com/community/tutorials/how-to-use-systemctl-to-manage-systemd-services-and-units)
    - can also run from `/etc/init.d/service start`
  - rsyslog is what we use to get the logs to papertrail
  - used the oracle version of Java 8

## Digital ocean
  - backups (auto) are different than snapshots (not auto) and different
  in pricing as well

## Chef
  - [ohai](https://docs.chef.io/ohai.html)
  - [`chef-shell`](https://docs.chef.io/chef_shell.html)
