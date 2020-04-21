# Networking 101

## Speed is a feature

|Delay|	User perception|
|----|----|
|0–100 ms	|Instant|
|100–300 ms	|Small perceptible delay|
|300–1000 ms|Machine is working|
|1,000+ ms	|Likely mental context switch|
|10,000+ ms	|Task is abandoned|

[source](https://hpbn.co/primer-on-web-performance/#speed-performance-and-human-perception)

Because faster sites mean

* better user engagement
* better user retention
* better conversion

> Transatlantic cable "[Hibernia Express](https://en.wikipedia.org/wiki/Hibernia_Express)" was laid between London and NewYork to give an edge of `~5 milliseconds` over other transatlantic cables

![Bandwidth & Latency](https://hpbn.co/assets/diagrams/9f12afe5ca29ba5c2ad555fcee5bd568.svg)

Latency is caused by

* **Propogation delay** = distance/speed of medium(light)
* **Transmission delay** = time required to push all data bits into the link
	* Transmitting 10MB data over 100Mbps link would be faster (0.8 sec) than sending it over 1Mbps link (80 sec). 10MB = 80Mb
* **Processing delay** = time taken by router to process the packet header, check for bit-level errors and determine packet's destination
* **Queuing delay** = time the packet waits in router's incoming buffer before it can be processed


Refractive Index = Speed of light / Speed of light in the medium
Eg., Refractive index of Optical fiber is \~1.4

Therefore, Max. possible speed of light = 200,000,000 m/sec

|Route|Distance|Latency|RTT|
|------|-----|-----|-----|
|NewYork to SanFrancisco| ~4000km | ~20ms |~40ms |
|NewYork to Amsterdam| ~6000km | ~30ms |~60ms |
|NewYork to Sydney| ~16000km | ~80ms |~160ms |
|Earth's Circumference| ~40000km | ~200ms |~200ms |

![](../images/NY-AMS.png)
![](../images/NY-SYD.png)

## TCP

TCP provides an effective abstraction of a reliable network running over an unreliable channel. It hides most of the complexity of network communication from our applications: 
* retransmission of lost data
* in-order delivery 
* congestion control and avoidance
* data integrity
* and more

TCP is optimized for accurate delivery, rather than a timely one.

### Three-way Handshake

![](https://hpbn.co/assets/diagrams/eefa1170a673da0140efe1ece7a2884b.svg)
Thus, each new connection will have a full roundtrip of latency before any application data can be transferred.

### Congestion Avoidance and Control

