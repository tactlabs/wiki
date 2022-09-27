/ [Home](index.md)

# HTTP response status codes

1. Informational responses (100–199)
2. Successful responses (200–299)
3. Redirection messages (300–399)
4. Client error responses (400–499)
5. Server error responses (500–599)

## 1. Informational responses

- 100   
This interim response indicates that the client should continue the request or ignore the response if the request is already finished.

- 101  
This code is sent in response to an Upgrade request header from the client and indicates the protocol the server is switching to.

- 102  
This code indicates that the server has received and is processing the request, but no response is available yet.  

- 103  
This status code is primarily intended to be used with the Link header, letting the user agent start preloading resources while the server prepares a response.

## 2. Successful responses  

- 201  
The request succeeded, and a new resource was created as a result. This is typically the response sent after POST requests, or some PUT requests.

- 202  
The request has been received but not yet acted upon. It is noncommittal, since there is no way in HTTP to later send an asynchronous response indicating the outcome of the request. It is intended for cases where another process or server handles the request, or for batch processing.

- 203  
This response code means the returned metadata is not exactly the same as is available from the origin server, but is collected from a local or a third-party copy. This is mostly used for mirrors or backups of another resource. Except for that specific case, the 200 OK response is preferred to this status.

- 204  
There is no content to send for this request, but the headers may be useful. The user agent may update its cached headers for this resource with the new ones.  

- 205
Tells the user agent to reset the document which sent this request.

- 206  
This response code is used when the Range header is sent from the client to request only part of a resource.  

- 207  
Conveys information about multiple resources, for situations where multiple status codes might be appropriate.

- 208  
Used inside a <dav:propstat> response element to avoid repeatedly enumerating the internal members of multiple bindings to the same collection.

- 226  
The server has fulfilled a GET request for the resource, and the response is a representation of the result of one or more instance-manipulations applied to the current instance.

## 3. Redirection messages

- 300  
The request has more than one possible response. The user agent or user should choose one of them. (There is no standardized way of choosing one of the responses, but HTML links to the possibilities are recommended so the user can pick.)

- 301  
The URL of the requested resource has been changed permanently. The new URL is given in the response.

- 302  
This response code means that the URI of requested resource has been changed temporarily. Further changes in the URI might be made in the future. Therefore, this same URI should be used by the client in future requests.  
 
- 303  
The server sent this response to direct the client to get the requested resource at another URI with a GET request.
 
- 305  
Defined in a previous version of the HTTP specification to indicate that a requested response must be accessed by a proxy. It has been deprecated due to security concerns regarding in-band configuration of a proxy.  

- 306  
This response code is no longer used; it is just reserved. It was used in a previous version of the HTTP/1.1 specification.  

- 307  
The server sends this response to direct the client to get the requested resource at another URI with same method that was used in the prior request. This has the same semantics as the 302 Found HTTP response code, with the exception that the user agent must not change the HTTP method used: if a POST was used in the first request, a POST must be used in the second request.  

- 308  
This means that the resource is now permanently located at another URI, specified by the Location: HTTP Response header. This has the same semantics as the 301 Moved Permanently HTTP response code, with the exception that the user agent must not change the HTTP method used: if a POST was used in the first request, a POST must be used in the second request.  

## 4. Client error responses

- 400  
The server cannot or will not process the request due to something that is perceived to be a client error (e.g., malformed request syntax, invalid request message framing, or deceptive request routing).  

- 401  
Although the HTTP standard specifies "unauthorized", semantically this response means "unauthenticated". That is, the client must authenticate itself to get the requested response.  

- 402  
This response code is reserved for future use. The initial aim for creating this code was using it for digital payment systems, however this status code is used very rarely and no standard convention exists.

- 403  
The client does not have access rights to the content; that is, it is unauthorized, so the server is refusing to give the requested resource. Unlike 401 Unauthorized, the client's identity is known to the server.  

- 404  
The server can not find the requested resource. In the browser, this means the URL is not recognized. In an API, this can also mean that the endpoint is valid but the resource itself does not exist. Servers may also send this response instead of 403 Forbidden to hide the existence of a resource from an unauthorized client. This response code is probably the most well known due to its frequent occurrence on the web.  

- 405  
The request method is known by the server but is not supported by the target resource. For example, an API may not allow calling DELETE to remove a resource.  

- 406  
This response is sent when the web server, after performing server-driven content negotiation, doesn't find any content that conforms to the criteria given by the user agent.  

- 407  
This is similar to 401 Unauthorized but authentication is needed to be done by a proxy.

- 408  
This response is sent on an idle connection by some servers, even without any previous request by the client. It means that the server would like to shut down this unused connection. This response is used much more since some browsers, like Chrome, Firefox 27+, or IE9, use HTTP pre-connection mechanisms to speed up surfing. Also note that some servers merely shut down the connection without sending this message. 

- 409  
This response is sent when a request conflicts with the current state of the server.  

- 410  
This response is sent when the requested content has been permanently deleted from server, with no forwarding address. Clients are expected to remove their caches and links to the resource. The HTTP specification intends this status code to be used for "limited-time, promotional services". APIs should not feel compelled to indicate resources that have been deleted with this status code.

- 411  
Server rejected the request because the Content-Length header field is not defined and the server requires it.  

- 412  
The client has indicated preconditions in its headers which the server does not meet.  

- 413  
Request entity is larger than limits defined by server. The server might close the connection or return an Retry-After header field.  


- 414  
The URI requested by the client is longer than the server is willing to interpret.

- 415  
The media format of the requested data is not supported by the server, so the server is rejecting the request.  

- 416  
The range specified by the Range header field in the request cannot be fulfilled. It's possible that the range is outside the size of the target URI's data.  

- 417  
This response code means the expectation indicated by the Expect request header field cannot be met by the server.  

- 418  
The server refuses the attempt to brew coffee with a teapot.


### Ref :

  * [http-response-status-reference](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status#client_error_responses)

