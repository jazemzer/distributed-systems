# Website Performance


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
* [Inlining](https://hpbn.co/http1x/#resource-inlining) 

--- 

**References**

* [High Performance Browser Networking - Oreilly](http://shop.oreilly.com/product/0636920028048.do) (book)
* [High Performance websites - Oreilly](http://shop.oreilly.com/product/9780596529307.do) (book)