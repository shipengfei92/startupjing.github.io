---
layout: post
title: Computer Network Two
description: Physical and Direct Link Layer
categories: blog
---

## Physical Layer Overview

### Scope of the physical layer
Concerns how signals are used to transfer message bits over a link; Carry analog signals to send digital bits. 
Topics includes:

* Properties of media: wires, wireless, fiber optics
* Simple signal propagation: bandwidth, attenuation, noise
* Modulation schemes: representing bits, noise
* Fundamental limits: nyquist, shannon

### Simple link model

* Diagram
![1](/images/CompNetwork/linkmodel.png)

* Concepts
Rate/bandwidth/capacity/speed in bits/second;
Delay in seconds related to length;
Other properties-whether broadcast and its error rate

### Message latency
Latency is the delay to send a message over a link

* Transmission delay
Time to put M-bit message on the wire = M/R

* Propagation delay
Time for bits to propagate across the wire = length/(2c/3) = D

* Total lantency
L = M/R + D

* A long link or a slow rate means high latency; Often one delay dominates

* Metric units
![2](/images/CompNetwork/unit.png)

### Bandwidth-delay product
* Messages take space on the wire
![3](/images/CompNetwork/len.png)
* Amout of data in flight is bandwidth-delay product BD = R * D


## Media
Media propagate signals that carry bits of information

* Wires: 
Twisted pair, Coaxial cable ...
* Fiver: 
High speed over long distances and total internal reflection; Two varities(multi-mode and single-model)
* Wireless: 
Send radiates signal over a region in many directions; Nearby signals interfere a a receiver and need to coordinate use


## Signals
What happen as signals propagate over the media

### Frequency representation
* A signal over time can be represented by its frequency components
![4](/images/CompNetwork/freq.png)
* Effect of less bandwidth
![5](/images/CompNetwork/lessfreq.png)

### Signals over a wire
What happens to a signal passing over a wire

* Signal is delayed
* Signal attenuated
* Frequencies above a cutoff are highly attenuated
* Noise added to the signal

![6](/images/CompNetwork/overwire.png)

### Signals over fiber
Lowe attentuation; High speed and large bindwidth

### Signals over wireless
* Signals transmitted on a carrier frequency
* Travel at speed of light, spread out and attentuate faster than 1/dist^2
* Multiple signals on the same frequency interfere at a receiver
* Interference leads to notion of spatial reuse of same frequency
![7](/images/CompNetwork/spatial.png)
* Wireless multipath
Signals bounce off objects and take multiple paths
![8](/images/CompNetwork/multipath.png)

## Modulation

### NRZ(non-return to zero) modulation
High voltage represents 1 and low voltage represents 0
![9](/images/CompNetwork/nrz.png)
Also can use more signal levels

### Clock recovery (4B/5B)
Map every 4 data bits into 5 code bits without long runs of zeros; Has at most 3 zeros in a row; Invert signal level on a 1 to break up long runs of 1s
![10](/images/CompNetwork/recover.png)

### Passband modulation
Signals need to be sent at higher frequencies; Passband modulation carries a signal by modulating a carrier;

* Carrier is simply a signal oscillating at a desired  frequency
* Can modulate by changing amplitude, frequency or phase
![11](/images/CompNetwork/passband.png)

## Limits

### Key channel properties
* Bandwidth B - limits the rate transitions
* Signal strength S and noise strength - limits how many signal levels we can distinguish

### Nyquist limit
* The maximum symbol rate is 2B
* If there are V signal levels, ignoring the noise, the maximum bit rate is R = 2B*logV

### 



[startupjing]:    http://startupjing.github.io  "startupjing"
[1]:    {{ page.url}}  ({{ page.title }})