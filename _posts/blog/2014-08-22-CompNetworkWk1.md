---
layout: post
title: Computer Network Week 1
description: Class Summary
categories: blog
---

## Uses of Networks

### Why we build networks
* For user communication: 
Enable remote communicate;
Need low latency for interactivity
* For resource sharing:
More cost effective than dedicated resources per user;
Network links are shared via `statistical multiplexing`
* Statistical Multiplexing:
Sharing of network bandwidth between users according to the statistics of their demand;
Userful because users are mostly idle and their traffic is bursty;
* For content delivery:
Same content delivered to many users;
More efficient than sending a copy all th way to each user--use `replicas`
* For computer communication:
Let computers interact with other computers;
Enable automated information procesing across different parties;
* For Connect computers to physical world:
Gathering sensor data and manipulate the world
* Value of connectivity:
Value of a network of n nodes is proportional to n^2;
Large network is more valuable than small one

## Network components

### Parts of a network
* App or user: use the network (Skype,Amazon)
* Host: support apps (laptop, mobile)
* Router: relay messages between links
* Link: connect nodes (wire, wireless)

### Type of links
* Full-duplex--bidirectional
* Half-duplex--bidirectional, but not both direction at the same time
* Simplex--unidirectional

### Wireless links
* Message is broadcast-received by all nodes in range
* Often show logical links-not all possible connectivity

### Network names by scale
* PAN-personal: bluetooth
* LAN-local: wifi, ethernet
* MAN-metropolitan: cable, DSL
* WAN-country: large ISP
* The Internet-network of all networks

### Network boundaries
* network part: host+router+link
* ISP part: router+link

### Key interfaces
* Apps-Network: define how apps use the network; sockets are widely used in practice
* Network-Network: define how nodes work together; 
traceroute can peek in the network



[startupjing]:    http://startupjing.github.io  "startupjing"
[1]:    {{ page.url}}  ({{ page.title }})





