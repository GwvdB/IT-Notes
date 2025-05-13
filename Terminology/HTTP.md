# HTTP
#networking #protocols #web

HTTP (Hypertext Transfer Protocol) is the foundation of data communication on the World Wide Web.

## Methods
See also: [[CURL#Method Examples]]

### GET
- Retrieves data from the specified resource
- Should not modify server state
- Data sent via URL parameters
- No request body
```http
GET /api/users?id=123 HTTP/1.1
Host: example.com
```

### POST
- Submits data to be processed to the specified resource
- Creates new resources
- Data sent in request body
```http
POST /api/users HTTP/1.1
Host: example.com
Content-Type: application/json

{
    "name": "John Doe",
    "email": "john@example.com"
}
```

### PUT
- Updates a specified resource entirely
- Idempotent (multiple identical requests should have same effect as single request)
```http
PUT /api/users/123 HTTP/1.1
Host: example.com
Content-Type: application/json

{
    "name": "John Doe",
    "email": "john@example.com",
    "age": 30
}
```

### PATCH
- Partially modifies a resource
- Only sends changed fields
```http
PATCH /api/users/123 HTTP/1.1
Host: example.com
Content-Type: application/json

{
    "email": "newemail@example.com"
}
```

### DELETE
- Removes specified resource
- Usually no request body
```http
DELETE /api/users/123 HTTP/1.1
Host: example.com
```

## Content Types
See also: [[CURL#Content Types]]

### Common MIME Types
- `application/json`: JSON data
- `application/xml`: XML data
- `application/x-www-form-urlencoded`: Form data
- `multipart/form-data`: File uploads
- `text/plain`: Plain text
- `text/html`: HTML content

## Status Codes

### 2xx Success
- 200: OK
- 201: Created
- 204: No Content

### 3xx Redirection
- 301: Moved Permanently
- 302: Found
- 304: Not Modified

### 4xx Client Errors
- 400: Bad Request
- 401: Unauthorized
- 403: Forbidden
- 404: Not Found
- 422: Unprocessable Entity

### 5xx Server Errors
- 500: Internal Server Error
- 502: Bad Gateway
- 503: Service Unavailable

## Headers

### Request Headers
- `Accept`: Expected response format
- `Authorization`: Authentication credentials
- `Content-Type`: Request body format
- `User-Agent`: Client identifier

### Response Headers
- `Content-Type`: Response format
- `Content-Length`: Response size
- `Cache-Control`: Caching directives
- `Set-Cookie`: Session cookies

## Authentication

### Common Methods
- Basic Authentication
- Bearer Token
- OAuth 2.0
- JWT (JSON Web Tokens)

## Related
- [[CURL]] - CURL usage and examples
- [[API]] - API documentation (if you have this note)
- [[REST]] - REST principles (if you have this note)