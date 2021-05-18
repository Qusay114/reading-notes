# HTTP Status Codes

### Status classes : 

* 100’s : Informational responses
* 200’s : Successful responses
* 300’s : Redirects
* 400’s : Client errors
* 500’s : Server errors 


### What is a status code 202? 
Accepted ,  If the operation is asynchronous and takes some time, which is the case in distributed systems, it can be appropriate to return this code with some information or URL to tell the client when the operation will be done .

### What is a status code 308?
Permanent Redirect - This tells the client to use another URL to access the resource and not use the current URL anymore. It’s helpful when we have multiple endpoints for one resource, but don’t want to implement reading from all of them.

### What code would you use if an update didn’t return data to a client? 
204 No Content .

### What code would you use if a resource used to exist but no longer does?
410 Gone - This is like 404 but we know that the resource existed in the past, but it got deleted or somehow moved, and we don’t know where.

### What is the ‘Forbidden’ status code?
403 Forbidden - The client has authorized or doesn’t need to authorize itself, but still has no permissions to access the resource.


# Build a REST API with Node.js, Express, & MongoDB :

### Why do we need to pull our MongoDB database string out of our server and put it into our .env?

So when upload to github you don’t send sensitive information to github. 

### Which is public to everyone on the internet.
What is middleware?

runs between request and response cycle, access to next function of request-response life cycle

### what does app.use(express.json()) do?
express. json() is a method inbuilt in express to recognize the incoming Request Object as a JSON Object. This method is called as a middleware in your application using the code: app. … urlencoded() is a method inbuilt in express to recognize the incoming Request Object as strings or arrays

### what does the /:id mean in a route?
The Route ID is a number which uniquely identifies the route. The name or title of a route is NOT unique. So if you want to refer to a specific route to mention a problem in an email, you better provide the Route ID.

### what is the difference beween PUT and PATCH?
The main difference between the PUT and PATCH method is that the PUT method uses the request URI to supply a modified version of the requested resource which replaces the original version of the resource, whereas the PATCH method supplies a set of instructions to modify the resource