# Numbers every programmer should know

## Latency Numbers `(~2020)`

| Event											| nano sec 	| micro sec | mill sec | Notes	|
| --------------------------------------------- |----------:| ---------:| ---------:|-------|
| L1 Cache reference      						| 1 		| 			| 	|				|
| Branch mispredict      						| 3 		| 			| 	|				|
| L2 Cache reference      						| 4 		| 			| 	| 4xL1			|
| Main memory/RAM reference						| 100 		| 			| 	| 25xL2, 100xL1	|
| Mutex Lock/Unlock      						| 17 		| 			| 	|				|
| Send 2000 bytes over commodity network		| 44 		| 			| 	|				|
| Compress 1 KB with Zippy						| 2,000		| 2			| 	|				|
| Read 1MB sequentially from main memory		| 3,000 	| 3			| 	|				|
| Read 1MB sequentially from SSD				| 49,000 	| 49		| 	| 16xmemory		|
| Read 1MB sequentially from disk				| 825,000 	| 825		| 	|16xSSD,275xmemory|
| Solid State Drive (SSD) random read			| 16,000 	| 16		| 	|				|
| Round trip network request in same data centre| 500000	| 500		| 	|				|
| Disk (Hard drive / magnetic drive) seek		| 2,000,000	| 2,000		|2 	|4xdata center round trip|
| Packet roundtrip from CA to Netherlands		| 150,000,000| 150,000	|150|				|



## For System Design Interviews

### Demographic
| Description				| Quantity		| Comparison 	|
| ------------------------- | ------------- | ----------|
| World population in 2019 	| 7.7 billion 	|			|
| Internet users			| 4.5 billion	| 60% 		|
| Social media users		| 3.8 billion	| 50% 		|
| Smartphone users			| 3.5 billion	| 45% 		|
| No. of software developers| 23 million	| 0.003% 	|

### Mobile usage
| Description				| Quantity		|
| ------------------------- | ------------- |
| No. of mobile connections | 9.5 billion 	|
| No. of unique mobile connections | 5.2 billion 	|
| Time on phone by avg. user | 90min/day |

### Monthly Active Users
| Application				| No of active users		|
| ------------------------- | ------------- |
| Facebook 					|2.4 billion |
| Youtube 					|2 billion |
| Whatsapp 					|1.6 billion |
| Wechat 					|1 billion |
| Instagram 				|1 billion |
| Tiktok 					|800 million | 
| Reddit 					|300 million |
| Twitter 					|300 million |

---

**References**

* [Update numbers - Medium](https://medium.com/@kousiknath/must-know-numbers-for-every-computer-engineer-6338a12c292c)
* [Interactive timeline ](https://colin-scott.github.io/personal_website/research/interactive_latency.html)

* [World population](https://www.worldometers.info/world-population/)
* [Mobile Phone statistics](https://www.bankmycell.com/blog/how-many-phones-are-in-the-world)
* [Internet statistics](https://www.statista.com/statistics/617136/digital-population-worldwide/)
* [Social network statistics](https://www.statista.com/statistics/272014/global-social-networks-ranked-by-number-of-users/)
* [Social media statistics](https://dustinstout.com/social-media-statistics/)