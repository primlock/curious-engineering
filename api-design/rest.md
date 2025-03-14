# REST

REST or representational state transfer is a software architecture style that defines a pattern for client/server communications over a network. REST is not a specification but a set of guidelines on how to architect a network-connected software system.

REST defines these architectural constraints:

* **Stateless**: The server won’t maintain any state between requests from the client
* **Client-server**: The client and server must be decoupled from each other, allowing each to develop independently.
* **Cacheable**: The data retrieved from the server should be cacheable either by the client or by the server.
* **Uniform Interface**: The server will provide a uniform interface for accessing resources without defining their representation.
* **Layered System**: The client may access the resources on the server indirectly through other layers such as a proxy or load balancer.
* **Code on Demand** (optional): The server may transfer code to the client that it can run, such as JavaScript for a single-page application.



### REST Web Services

A REST web service is any web service that adheres to REST architecture constraints. These web services expose their data to the outside world through an API. REST APIs provide access to web service data through public web URLs.

#### HTTP Methods

REST APIs listen for HTTP methods like **GET**, **POST**, and **DELETE** to know which operations to perform on the web service’s resources.

#### Status Codes

Once a REST API receives and processes an HTTP request, it will return an HTTP response. Included in this response is an HTTP [status code](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status). This code provides information about the results of the request.

Some of the most common status codes you've likely seen are:

* **200 OK**: The request made succeeded.
* **403 Forbidden**: The client does not have access rights to the content
* **404 Not Found**: The server cannot find the requested resource.
* **500 Internal Server Error**: The server has encountered a situation it does not know how to handle.

#### Endpoints

A REST API exposes a set of public URLs that client applications use to access the resources of a web service. These URLs, in the context of an API, are called endpoints.

| Method   | Endpoint                   | Description                 |
| -------- | -------------------------- | --------------------------- |
| `GET`    | `/customers`               | Get a list of customers     |
| `GET`    | `/customers/<customer_id>` | Get a single customer       |
| `POST`   | `/customers`               | Create a new customer       |
| `PUT`    | `/customers/<customer_id>` | Update a customer           |
| `PATCH`  | `/customers/<customer_id>` | Partially update a customer |
| `DELETE` | `/customers/<customer_id>` | Delete a customer           |

### Building APIs

It’s very unlikely that your REST API will stay the same throughout the life of your web service. Resources will change, and you’ll need to update your endpoints to reflect these changes. This is where API versioning comes in. API versioning allows you to modify your API without fear of breaking existing integrations. URI versioning and HTTP header versioning are examples of API versioning.

### References

* Schooneveld, J. V. (2021, July 28). _Python and REST APIs: Interacting With Web Services_. Real Python. [https://realpython.com/api-integration-in-python/](https://realpython.com/api-integration-in-python/)
* MDN Contributers. (2024, July 25). _HTTP response status codes_. MDN Web Docs. [https://developer.mozilla.org/en-US/docs/Web/HTTP/Status](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)
