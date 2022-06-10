# Network Protocols

### IP

Stands for **Internet Protocol**. Other protocol like TCP, HTTP or UDP are built on top of that.

<img src="../../.gitbook/assets/file.drawing (3).svg" alt="IP Packet" class="gitbook-drawing">

* IP Packets are made-up of Bytes and contains
  * IP Header (20-60 Bytes)
    * Source IP Address
    * Destination IP Address
    * Total Size of packet
    * IP Version (currently - IPv4, IPv6)
* IP Packets does not guaranteed order of packets (at destination)
* IP Packets does not guaranteed delivery

### TCP

Transmission Control Protocol&#x20;

#### **Features**

<img src="../../.gitbook/assets/file.drawing (1).svg" alt="IP Packet with TCP Header and data" class="gitbook-drawing">

****

* Guaranteed order of packets at destination
* Guaranteed delivery of packets (or at least resends)
* Received without data corruption (in case of loss or corruption, it resends it)

#### TCP Handshake

* SYNC
* ACK & SYNC
* ACK



Allows for ordered, reliable data delivery between machines over the public internet by creating a connections.

TCP is usually implemented in the kernel, which exposes sockets to applications that they can use to stream data through an open connection.

### HTTP/1.1

[W3 RFC](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html)

The **H**yper**T**ext **T**ransper **P**rotocol is very common network protocol implemented on top of TCP.&#x20;

* Safe Methods
* **Idempotent Methods**\
  Methods can also have the property of "idempotence" in that (aside from error or expiration issues) the side-effects of N > 0 identical requests is the same as for a single request. The methods GET, HEAD, PUT and DELETE share this property. Also, the methods OPTIONS and TRACE SHOULD NOT have side effects, and so are inherently idempotent.
*

#### HTTP Verbs

* **OPTIONS**\
  A request for information about the communication options available on the request/response chain identified by the Request-URI
* **GET**\
  Retrieve information (in the form of an entity) is identified by the Request-URI
* **HEAD**
* **POST**
* **PUT**
* **DELETE**
* **TRACE**
* **CONNECT**

#### Status Codes

[MDN Docs](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)

1. [Informational responses](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#information\_responses) (`100`–`199`)
2. [Successful responses](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#successful\_responses) (`200`–`299`)
3. [Redirection messages](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#redirection\_messages) (`300`–`399`)
4. [Client error responses](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#client\_error\_responses) (`400`–`499`)
5. [Server error responses](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#server\_error\_responses) (`500`–`599`)

WebDAV - Web Distributed Authoring and Versioning

* 100 Continue
* 101 Switching Protocols (For upgrade request headers)
* 102 Processing (WebDAV)
* 103 Early Hints (Link header - start preloading resources)
* 200 OK (Get, Head, Put, Post, Trace)
* 201 Created (Post, Put)
* 202 Accepted (mostly for batch processing)
* 203 Non-Authoritative Information (Used by mirrors or backups for 200 OK responses)
* 204 No Content
* 205 Reset Content
* 206 Partial Content (when range header is present, requests partial content)
* 207 Multi Status (WebDAV)
* 208 Already Reported (WebDAV)
* 226 IM Used (HTTP Delta Encoding)
* 300 Multiple Choices
* 301 Moved Permanently
* 302 Found
* 303 See Other
* 304 Not Modified
* 305 Use Proxy (Deprecated)
* 306 (Unused and reserved)
* 307 Temporary Redirect (similar to 302 + method should not change)
* 308 Permanent Redirect (`Location` header, similar to 301 + method should not change)
* 400 Bad Request
* 401 Unauthorized (semantically Unauthenticated)
* 402 Payment Required (Experimental, for future use)
* 403 Forbidden (Does not have access rights. Unlike 401, the client's identity is known to the server)
* 404 Not Found
* 405 Method Not Allowed (method is known by the server, but is not supported by the target resource)
* 406 Not Acceptable (Server driven content negotiations doesn't find any content that conforms to the criteria. Eg. - requesting csv, when api only supports json and xml)
*

#### UDP
