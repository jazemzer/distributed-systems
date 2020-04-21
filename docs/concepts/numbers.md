# Numbers every programmer should know

## Latency Numbers `(~2020)`

| Event											| nano sec 	| micro sec | mill sec | Notes	|
| --------------------------------------------- |----------:| ---------:| ---------:|-------|
| L1 Cache reference      						| 1 		| 			| 	|				|
| L2 Cache reference      						| 4 		| 			| 	| 4xL1			|
| Main memory/RAM reference						| 100 		| 			| 	| 25xL2, 100xL1	|
| Read 1MB sequentially from main memory		| 3,000 	| 3			| 	|				|
| Read 1MB sequentially from SSD				| 49,000 	| 49		| 	| 16xmemory		|
| Read 1MB sequentially from disk				| 825,000 	| 825		| 	|16xSSD,275xmemory|
| Round trip network request in same data centre| 500000	| 500		| 	|				|
| Disk (Hard drive / magnetic drive) seek		| 2,000,000	| 2,000		|2 	|4xdata center round trip|
| Packet roundtrip from CA to Netherlands		| 150,000,000| 150,000	|150|				|
| Branch mispredict      						| 3 		| 			| 	|				|
| Mutex Lock/Unlock      						| 17 		| 			| 	|				|
| Send 2000 bytes over commodity network		| 44 		| 			| 	|				|
| Compress 1 KB with Zippy						| 2,000		| 2			| 	|				|
| Solid State Drive (SSD) random read			| 16,000 	| 16		| 	|				|

---

**References**

* [Interactive timeline ](https://colin-scott.github.io/personal_website/research/interactive_latency.html)
* [Updated numbers - Medium](https://medium.com/@kousiknath/must-know-numbers-for-every-computer-engineer-6338a12c292c)
