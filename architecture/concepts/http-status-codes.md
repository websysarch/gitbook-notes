# HTTP Status Codes

### 100

#### **100 Continue**

#### **101 Switching Protocols** (For upgrade request headers)

#### 102 Processing (WebDAV)

#### **103 Early Hints** (Link header - start preloading resources)

### 200

#### **200 OK** (Get, Head, Put, Post, Trace)

#### **201 Created** (Post, Put)

#### **202 Accepted** (mostly for batch processing)

#### **203 Non-Authoritative Information** (Used by mirrors or backups for 200 OK responses)

#### **204 No Content**

#### **205 Reset Content** Reset the document, which sent this request

#### **206 Partial Content** (when range header is present, requests partial content)

#### 207 Multi Status (WebDAV)

#### 208 Already Reported (WebDAV)

#### 226 IM Used (HTTP Delta Encoding)

### 300

#### **300 Multiple Choices** The request has more than one possible response.

#### **301 Moved Permanently**

#### **302 Found**

#### **303 See Other**

#### **304 Not Modified**

#### 305 Use Proxy (Deprecated)

#### 306 (Unused and reserved)

#### **307 Temporary Redirect** (similar to 302 + method should not change)

#### **308 Permanent Redirect** (`Location` header, similar to 301 + method should not change)

### 400

#### **400 Bad Request**

#### **401 Unauthorized** (semantically Unauthenticated)

#### 402 Payment Required (Experimental, for future use)

#### **403 Forbidden** (Does not have access rights. Unlike 401, the client's identity is known to the server)

#### **404 Not Found**

#### **405 Method Not Allowed** (method is known by the server, but is not supported by the target resource)

#### **406 Not Acceptable** (Server driven content negotiations doesn't find any content that conforms to the criteria. Eg. - requesting csv, when api only supports json and xml)

#### 407 Proxy Authentication Required (Similar to 401, but needs to be done by proxy)

#### 408 Request Timeout

#### 409 Conflict

#### 410 Gone

#### 411 Length Required

#### **412 Precondition Failed** The client has indicated preconditions in its headers which the server does not meet

#### 413 Payload Too Large

#### 414 URI Too Long: The URI requested by the client is longer than the server is willing to interpret

#### 415 Unsupported Media Type

#### 416 Range Not Satisfiable

#### 417 Expectation Failed

#### 418 I'm a teapot

#### 421 Misdirected Request

#### 422 Un-processable Entity

#### 423 Locked

#### 424 Failed Dependency

#### 425 Too Early

#### 426 Upgrade Required

#### 428 Precondition Required

#### 429 Too Many Requests

#### 431 Request Header Fields Too Large

#### 451 Unavailable For Legal Reasons

### 500

#### 500 Internal Server Error

#### 501 Not Implemented

#### 502 Bad Gateway

#### 503 Service Unavailable

#### 504 Gateway Timeout

#### 505 HTTP Version Not Supported

#### 506 Variant Also Negotiates

#### 507 Insufficient storage

#### 508 Loop Detected

#### 510 Not Extended

#### 511 Network Authentication Required

