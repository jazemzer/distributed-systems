# HTTP/2


## HTTP1.1 limitations

* [Head of line blocking](https://en.wikipedia.org/wiki/Head-of-line_blocking) problem
	* [HTTP pipelining](https://en.wikipedia.org/wiki/HTTP_pipelining) allows all requests to be sent at once without waiting for the response. But that didn't solve the problem because servers still needed to respond in order
* Inefficient use of TCP connections
	* Protocol allows only one outstanding request per TCP connection. Therefore, browsers need multiple TCP connections for parallelism but that causes TCP congestion. Hence, browser place a limit on concurrent download per domain (between 2-16)
* Fat HTTP headers without any compression
	* Cookie


## How was limitations of HTTP/1.1 handled?
* Head of line blocking was worked around by [domain sharding](https://www.keycdn.com/support/domain-sharding)
* Using CSS sprites that combine multiple images into a single one so that they're loaded in a single HTTP request
* Inlining JS and CSS
* Gzipping
* Multiple CDNs

## How is HTTP/2 better than HTTP/1.1

* HTTP/2 is a single TLS encrypted connection
* Request/Response are a logical stream. These streams are chopped into header and data frames and multiplexed on the same connection avoiding head of line blocking
* Headers are heavily compressed (HPack) to benefit repeated http requests
* Server push

## Best practices of Web performance

* Optimize DNS Lookups
	* Limit the number of unique domain names
	* Ensure low DNS resolution latencies
	* Leverage [DNS pre-fetch](https://developer.mozilla.org/en-US/docs/Web/Performance/dns-prefetch)
* Optimie TCP connections
	* Leverage [Preconnect](https://www.keycdn.com/support/preconnect) which sets up early connections before an HTTP request is actually sent to the server
	* Use a CDN closer to user. This indirectly reduces the RTT for the TCP connection
	* Implement latest [TLS best practices](https://istlsfastyet.com/)
	* Avoid Redirects - that usually causes connection to new hostnames
* Cache on client - TTL
	* Cache images forever
	* CSS/JS - cache for twice the median session time so it is relatively fresh
* Use conditional caching
	* Using [ETag](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/ETag) that uniquely identifies the object so server can return HTTP 304 if it is requested again
	* Using [If-modified-since](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/If-Modified-Since) in http request so server can return HTTP 304
* Compression and Minification
	* All text content (Html,JS,CSS,Json) benefit from compresison - gzip, deflate
* Avoid Blocking CSS/JS
	* Add all the CSS elements in the head section
	* Use 'async' attribute for JS than be downloaded parallely while HTML is being parsed but before the DOM is loaded
	* Use 'defer' attribute for JS that can be run after DOM is loaded
* Optimize Images
	* Remove metadata like location, timestamp, image dimension, resolution 
	* Scaling images for different viewport


## Anitpatterns with HTTP/2
* Domain Sharding as that creates multiple TCP connections 
* CSS Spriting
* Concatenation of files
* Inlining 


---

**References**

* [HTTP/2 101 video - Chrome Dev summit](https://www.youtube.com/watch?v=r5oT_2ndjms)
* [HTTP Data size](https://httparchive.org/reports/state-of-the-web)