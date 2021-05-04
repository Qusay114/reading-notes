# REST API :
rest stands for Representational state transfer , which is a software architectural style which uses a subset of HTTP. It is commonly used to create interactive applications that use Web services. A Web service that follows these guidelines is called RESTful.
REST APIs are designed around resources, which are any kind of object, data, or service that can be accessed by the client.
A resource has an identifier, which is a URI that uniquely identifies that resource. For example, the URI for a particular customer order might be:

	    https://adventure-works.com/orders/1


The most common HTTP verbs are GET, POST, PUT, PATCH, and DELETE.resource URIs should be based on nouns (the resource) and not verbs (the operations on the resource). 
Good Url : 

	    https://adventure-works.com/orders.

GET: A successful GET method typically returns HTTP status code 200 (OK). If the resource cannot be found, the method should return 404 (Not Found).

POST:If a POST method creates a new resource, it returns HTTP status code 201 (Created).

DELETE: If the delete operation is successful, the web server should respond with HTTP status code 204, indicating that the process has been successfully handled, but that the response body contains no further information. If the resource doesn't exist, the web server can return HTTP 404 (Not Found).
