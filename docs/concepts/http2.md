# HTTP/2


## HTTP1.1 limitations

* [Head of line blocking](https://en.wikipedia.org/wiki/Head-of-line_blocking) problem
	* [HTTP pipelining](https://en.wikipedia.org/wiki/HTTP_pipelining) allows all requests to be sent at once without waiting for the response. But that didn't solve the problem because servers still needed to respond in order
* Inefficient use of TCP connections
	* Protocol allows only one outstanding request per TCP connection. Therefore, browsers need multiple TCP connections for parallelism but that causes TCP congestion. Hence, browser place a limit on concurrent download per domain (between 2-16)
* Fat HTTP headers without any compression
	* Cookie


## How did applications handle HTTP/1.1 limitations?
* Head of line blocking was worked around by [domain sharding](https://www.keycdn.com/support/domain-sharding)
* Using CSS sprites that combine multiple images into a single one so that they're loaded in a single HTTP request
* Inlining JS and CSS
* Gzipping
* Multiple CDNs

## How is HTTP/2 better than HTTP/1.1

* HTTP/2 is a single TLS encrypted connection
* Request/Response are a logical stream. Each streams is chunked into header and data frames and multiplexed on the same connection avoiding head of line blocking
* Headers are heavily compressed (HPack) to benefit repeated http requests
* Server push

### 1. Framing in HTTP/2
![HTTP/2 Message stream](https://developers.google.com/web/fundamentals/performance/http2/images/streams_messages_frames01.svg)

### 2. Stream Multiplexing
![Stream Multiplexing](https://developers.google.com/web/fundamentals/performance/http2/images/multiplexing01.svg)

### 3. Header Compression
Uses Huffman Coding
![Header compression](https://developers.google.com/web/fundamentals/performance/http2/images/header_compression01.svg)

### 4. Server push
![Server push](https://developers.google.com/web/fundamentals/performance/http2/images/push01.svg)

---

**References**

* [HTTP/2 101 - Chrome Dev summit](https://www.youtube.com/watch?v=r5oT_2ndjms) (video)
* [HTTP/2 performance - Google](https://developers.google.com/web/fundamentals/performance/http2)
* [Learning HTTP/2 - Oreilly](http://shop.oreilly.com/product/0636920052326.do) (book)
* [High Performance Browser Networking - Chapter](https://hpbn.co/http2/) (book)

