## Data formats 

JSon

## Http methods

| Method  | desc                                                       |
| ------- | ---------------------------------------------------------- |
| GET     | GET A RESOURCE FROM THE SERVER                             |
| POST    | Post a resource to the server                              |
| PUT     | put a resource onto the server (overwrite)                 |
| PATCH   | Update parts of an existing resource on the server         |
| DELETE  | Delete a resource on the server                            |
| OPTIONS | Determine whether follow-up is allowed(send automatically) |


## Rest principles

**Uniform interface**: clearly defined API endpoints with clearly defined request + response data structure
**Stateless interactions** server and client don't store any connection history, every request is handled separately

*Cacheable* servers may set caching headers to allow the client to cache responses. 
*Client-server* server and client are separated, client is not concerned with persisten data storage. 
*layered system* server may forward request to other apis
*Code on demand* executable code may be transferred from server to client 

