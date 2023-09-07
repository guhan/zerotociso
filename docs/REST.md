# REST API

## What is a restful API?
A RESTful API (Representational State Transfer API) is an architectural style for designing networked applications, particularly web services, that adhere to a set of principles and constraints. It provides a standardized approach for building scalable, stateless, and interoperable web APIs.

RESTful APIs are based on the following key principles:
- **Client-Server Architecture**: The client and server are separate entities that communicate over a network. The client initiates requests to the server, which processes the requests and sends back responses.


- **Stateless Communication**: Each request from the client to the server contains all the necessary information to understand and process the request. The server does not maintain any client-specific context between requests. Each request is treated independently.


- **Uniform Interface**: RESTful APIs use a uniform set of well-defined methods and standard protocols to interact with resources. The common HTTP methods (GET, POST, PUT, DELETE, etc.) are often used to perform CRUD (Create, Read, Update, Delete) operations on resources.


- **Resource-Oriented**: Resources are the key concept in a RESTful API. Resources are typically represented by URLs (Uniform Resource Locators) and can be accessed and manipulated using the standard HTTP methods. For example, a user resource can be represented by the URL "/users" and accessed via GET, POST, PUT, DELETE methods.


- **Stateless Responses**: Each response from the server to the client contains the necessary information to understand and process the response. The server does not maintain any client-specific state between responses.


- **Hypermedia as the Engine of Application State (HATEOAS)**: HATEOAS is an important principle in RESTful APIs. It means that the server includes links or hypermedia in the response, allowing clients to navigate and discover available resources and actions dynamically.
