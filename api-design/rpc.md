# Remote Procedure Call (RPC)

A server can itself be a client to another service. This approach is often used to decompose a large application into smaller services by area of functionality, such that one service makes a request to another when it requires some functionality or data from that other service. This way of building applications has traditionally been called a service-oriented architecture (SOA), more recently refined and rebranded as microservices architecture.

These services can talk to one another through RPC which attempts to make the communication between services look the same as a function call inside of one service. This can create problems because a remote request can have different outcomes than a local function call. This includes:
* A network request being unpredictable; the request or response may be lost due to a network problem, or the remote machine may be slow or unavailable, and such problems are entirely outside of your control.
* A network request may return without a result, due to a timeout. In that case, you simply don’t know what happened.
* A network request is much slower than a function call, and its latency is also wildly variable.
* The client and the service may be implemented in different programming languages, so the RPC framework must translate datatypes from one language into another.

### Comparing REST and RPC

Custom RPC protocols with a binary encoding format (like gRPC) can achieve better performance than something generic like JSON over REST. However, a RESTful API has other significant advantages:
* Its good for experimentation and debugging.
* Its supported by all main-stream programming languages and platforms
* There is a vast ecosystem of tools available for REST (servers, caches, load balancers, proxies, firewalls, monitoring, debugging tools, testing tools, etc.).

For these reasons, REST seems to be the predominant style for public APIs. The main focus of RPC frameworks is on requests between services owned by the same organization, typically within the same datacenter.

### gPRC

gRPC is a modern open source high performance Remote Procedure Call (RPC) framework that can run in any environment. It can efficiently connect services in and across data centers with pluggable support for load balancing, tracing, health checking and authentication.

In gRPC, a client application can directly call a method on a server application on a different machine as if it were a local object, making it easier for you to create distributed applications and services. As in many RPC systems, gRPC is based around the idea of defining a service, specifying the methods that can be called remotely with their parameters and return types. On the server side, the server implements this interface and runs a gRPC server to handle client calls. On the client side, the client has a stub (referred to as just a client in some languages) that provides the same methods as the server.

<img alt="gRPC-Client-Server" src="figures/gRPC-server-stub.svg"  width=60%>

gRPC clients and servers can run and talk to each other in a variety of environments and can be written in any of gRPC’s supported languages.

#### Protocol Buffers

By default, gRPC uses Protocol Buffers. Protocol Buffers are a language-neutral, platform-neutral extensible mechanism for serializing structured data. It’s like JSON, except it’s smaller and faster, and it generates native language bindings. You define how you want your data to be structured once, then you can use special generated source code to easily write and read your structured data to and from a variety of data streams and using a variety of languages.

The first step when working with protocol buffers is to define the structure for the data you want to serialize in a proto file: this is an ordinary text file with a `.proto` extension. Protocol buffer data is structured as messages, where each message is a small logical record of information containing a series of name-value pairs called fields.

```proto
message Person {
  string name = 1;
  int32 id = 2;
  bool has_ponycopter = 3;
}
```

Then, once you’ve specified your data structures, you use the protocol buffer compiler `protoc` to generate data access classes in your preferred language(s) from your proto definition. 

These provide simple accessors for each field, like `name()` and `set_name()`, as well as methods to serialize/parse the whole structure to/from raw bytes. So, for instance, if your chosen language is C++, running the compiler on the example above will generate a class called `Person`. You can then use this class in your application to populate, serialize, and retrieve `Person` protocol buffer messages.

### References

* Kleppmann, M. (2017). _Designing Data-Intensive Applications_. O'Reilly Media. 

* gRPC Authors. (2024, July 25). _Introduction to gRPC_. gRPC. [https://grpc.io/docs/what-is-grpc/introduction/](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)

* Google LLC. (2024). _Overview_. Protocol Buffers Documentation. [https://protobuf.dev/overview/](https://protobuf.dev/overview/)