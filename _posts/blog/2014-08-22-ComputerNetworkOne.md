---
layout: post
title: Computer Network One
description: Introduction, Protocols and Layering
categories: blog
---


This is the summary of week one.


## Uses of Networks

### Why we build networks

* For user communication: 
Enable remote communicate;
Need low latency for interactivity
* For resource sharing:
More cost effective than dedicated resources per user;
Network links are shared via `statistical multiplexing`
* For content delivery:
Same content delivered to many users;
More efficient than sending a copy all th way to each user--use `replicas`
* For computer communication:
Let computers interact with other computers;
Enable automated information procesing across different parties;
* For Connect computers to physical world:
Gathering sensor data and manipulate the world

### Some Concepts

* Statistical Multiplexing:
Sharing of network bandwidth between users according to the statistics of their demand;
Userful because users are mostly idle and their traffic is bursty;
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


## Sockets

### Network-Application Interface
let apps talk to each other via hosts and hide details of the network

### Motivating Application
* Simple client-server setup: file transfer, web browsing, echo

### Socket API
* Sockets let apps attach to the local network at different ports

* API table
![test1](/images/CompNetwork/APItable.png)

### Using Sockets
* Main Process
![test2](/images/CompNetwork/process.png)

* Process with API calls (* is block calls)
![test3](/images/CompNetwork/processwithcall.png)

## Traceroute
Network service API hides details--Apps talk to each other with no real idea inside network.

### How it works
Probes successive hops to find network path from local host to remote host

![test4](/images/CompNetwork/traceroute.png)

### Using traceroute
On terminal: type `traceroute www.example.com`


## Protocol Layers
Networks need modularity. We need manage complexity.

### Protocol and Layers
Protocols and layers is the main structuring method used to divide up network functionality.

* Each instance of a protocal talks virtually to its peer using the protocol

* Each instance of a protocol uses only the services of the lower layer

* Basic diagram
![test5](/images/CompNetwork/protocl.png)

* Protocol stack
![test6](/images/CompNetwork/protocolstack.png)

### Encapsulation
* Encapsulation is the mechanism used to effect protocol layering. 

* Lower layers wraps higher layer content, adding ites own information to make a new message for delivery.
![test7](/images/CompNetwork/encapsulation.png)

### Demultiplexing
* Incoming message must be passed to the protocols that it uses.

* Demultiplexing keys
![test8](/images/CompNetwork/demultiplexing.png)

### Advantage of Layering
* Information hiding and reuse
![test9](/images/CompNetwork/adv1.png)

* Using information to connect different systems
![test10](/images/CompNetwork/adv2.png)

### Disadvantage of Layering
* Adds overhead but minor for long messages
* Hides information: App might care whether running over wired or wireless




## Ending

[startupjing]:    http://startupjing.github.io  "startupjing"
[1]:    {{ page.url}}  ({{ page.title }})