# Hypertext Transfer Protocol (HTTP)

HTTP is an application layer protocol for fetching resources such as HTML documents. It is the foundation of any data exchange on the Web and it is a client-server protocol, which means requests are initiated by the recipient, usually the Web browser. A complete document is reconstructed from the different sub-documents fetched, for instance, text, layout description, images, videos, scripts, and more. Clients and servers communicate by exchanging individual messages (as opposed to a stream of data). The messages sent by the client, usually a Web browser, are called requests and the messages sent by the server as an answer are called responses.[^1] 

<img alt="Reconstructing the web browser with HTTP" src="figures/http-fetching-page.png"  width=80%>

HTTP is sent over TCP but any transport layer protocol can be used (HTTP/3 uses UDP). It can be used to fetch more than just hypertext documents such as images, videos and posting content to servers.

### HTTP Aspects

HTTP was designed to be a simple and human readable (HTTP 1.1 and earlier). HTTP itself is **stateless**, which means that there is no link between two request on the same connection. Instead, there are *HTTP cookies* to allow the use of stateful sessions. This allows sessions created on each HTTP request to share the same state.

### What can HTTP Control

Here are some of the things that HTTP can control:
* Caching: How documents are cached can be controlled by HTTP. The server can instruct proxies and clients about what to cache and for how long
* Authentication: Basic authentication may be provided by HTTP, either using the WWW-Authenticate and similar headers, or by setting a specific session using HTTP cookies.
* Sessions: Using HTTP cookies allows you to link requests with the state of the server. This creates sessions, despite basic HTTP being a state-less protocol.

### HTTP Messages

While HTTP messages defined in HTTP/1.1 and earlier are human readable, in HTTP/2 they are embedded into a binary structure called a frame. This allows for optimizations such as compression and multiplexing.

There are two types of HTTP messages; **requests** and **responses**.

#### Requests

An HTTP request has the following elements:

<img alt="HTTP request diagram" src="figures/http-request.png" width="55%">

##### Methods

This describes the action that the client would like to perform.[^2]

| Method    | Description                                                                                   |
| --------- | --------------------------------------------------------------------------------------------- |
| `GET`     | A request for a representation of the specified resource.                                     |
| `HEAD`    | A request for a representation of the specified resource without the response body.           |
| `POST`    | A submission of data to the specified resource.                                               |
| `PUT`     | A replacement of the current representations of the target resource with the request payload. |
| `PATCH`   | This method applies partial modifications to a resource.                                      |
| `DELETE`  | This method deletes the specified resource.                                                   |
| `CONNECT` | This method establishes a tunnel to the server identified by the target source.               |
| `OPTIONS` | This method describes the communication options for the target resource.                      |
| `TRACE`   | This method performs a message loop-back test along the path to the target resource.          |

##### Path 

The path of the resource to fetch; its the URL of the resource without the obvious elements (protocol, domain or port).

##### Version 

This is the version of the HTTP protocol.

##### Headers

This is a field that lets the client and the server exchange additional information with an HTTP request or response[^3].

##### Body

Applies to some methods like POST, similar to those in responses which contain the resource sent.

#### Response

An HTTP response has the following elements:

<img alt="HTTP response diagram" src="figures/http-response.png" width="55%">

##### Version 

This is the version of the HTTP protocol.

##### Status Code 

This is the code indicating if the request was successful or not, and why.

##### Status Message 

A short description of the status code.

##### Headers

See request headers.

##### Body

See request body.

[^1]: MDN Contributers. (2024, September 2). _An overview of HTTP_. MDN Web Docs. [https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)

[^2]: MDN Contributers. (2024, September 12). _HTTP request methods_. MDN Web Docs. [https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)

[^3]: MDN Contributers. (2024, October 22). _HTTP headers_. MDN Web Docs. [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)