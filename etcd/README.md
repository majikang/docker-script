etcd
============

Build etcd cluster with docker-compose.

Prerequisites
-------------

Add the following hosts

    172.16.238.11 etcd-0
    172.16.238.12 etcd-1
    172.16.238.13 etcd-2

Add the following aliases

    $ sudo ifconfig lo0 alias 172.16.238.11
    $ sudo ifconfig lo0 alias 172.16.238.12
    $ sudo ifconfig lo0 alias 172.16.238.13

Usage
-----

Start the cluster:

    $ docker-compose up -d

Stop the cluster:

    $ docker-compose down

Verify the cluster's health:

    $ source .env
    $ etcdctl --endpoints ${ENDPOINTS} cluster-health
