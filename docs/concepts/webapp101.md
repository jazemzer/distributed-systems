# WebApp 101

### Difference between n-tier and n-layer 
Tier - physical separation at the component level and not at the code level

### 5 different HTTP push mechanisms

* Ajax long polling
* Web Sockets 
	* bi-directional
	* chat, browser games, social streams
* HTML5 Event Source API (frontend) & Server sent events (backend)
	* uni-directional
	* realtime feeds - twitter, etc
* HTML5 Streaming API
	* chunked video streaming
* Message queues

### What is Scalability
Ability to handle increased workload without sacrificing latency

### Scalability Bottlenecks

* Scaling DB 
* Absence of Asynchronocity
* Not using Caching (wisely)
* Incorrect setup of Load balancers
* Code-level issues

### What is HA
High availability (HA) is the ability of the system to stay online despite having failures at the infrastructural level in real-time.

Reasons:

* Hardware
* Software
* Human errors

### How to achieve HA

* Redundancy - Active Passive HA mode
	- Redundancy is duplicating the components or instances & keeping them on standby to take over in case the active instances go down. It’s the fail-safe, backup mechanism.
* Replication - Active Active HA mode
	- Replication means having a number of similar nodes running the workload together. There are no standby or passive instances. 

### Types of Load balancing 

* DNS load balancing
	- DNS load balancing enables the authoritative server to return different IP addresses of a certain domain to the clients. Every time it receives a query for an IP, it returns a list of IP addresses of a domain to the client.
* Hardware
* Software
	- HAproxy

### Different load balancing algorithms

* (Weighted) Round-robin
* Least connections
* Random
* Hash


### Types of Databases

* Document-oriented
	- Product catalogue
	- News feed
	- Web based games
* Graph
* Key value
* Wide column
* Time series
* Relational	

### Caching Strategies

* Cache aside
	- Data loaded lazily
	- Suitable for read-heavy loads
* Read through
	- Similar to cache-aside but cache is always consistent with database
* Write through
	- Write to cache before DB 
	- Small latency overhead
* Write back
	- Data only written to cache 
	- After a delay, it is written to db in bulk


### TODO
* HTML5 Event Source API (frontend) & Server sent events (backend)
* HTML5 Streaming API
* HA Clustering