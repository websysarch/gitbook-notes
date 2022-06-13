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

<img src="../../.gitbook/assets/file.drawing (1) (1).svg" alt="IP Packet with TCP Header and data" class="gitbook-drawing">

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

* ****

#### UDP
