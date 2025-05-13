# CURL
#networking #http #tools

CURL (Client URL) is a command-line tool for transferring data using various protocols. This note focuses on HTTP/HTTPS usage.

## Basic Syntax
```bash
curl [options] <url>
```

## Common Options
- `-X, --request`: Specify HTTP method (see [[HTTP#Methods]])
- `-H, --header`: Add HTTP header
- `-d, --data`: Send data in POST request
- `-F, --form`: Submit form data
- `-i, --include`: Include response headers
- `-I, --head`: Fetch headers only
- `-o, --output`: Write output to file
- `-v, --verbose`: Verbose output

## Method Examples

### GET Request
```bash
curl -X GET "https://api.example.com/users" \
  -H "Authorization: Bearer token123"
```
See also: [[HTTP#GET]]

### POST Request
```bash
curl -X POST "https://api.example.com/users" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "John Doe",
    "email": "john@example.com"
  }'
```
See also: [[HTTP#POST]]

### PUT Request
```bash
curl -X PUT "https://api.example.com/users/123" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "John Doe Updated"
  }'
```
See also: [[HTTP#PUT]]

### PATCH Request
```bash
curl -X PATCH "https://api.example.com/users/123" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "John Doe Patched"
  }'
```
See also: [[HTTP#PATCH]]

### DELETE Request
```bash
curl -X DELETE "https://api.example.com/users/123"
```
See also: [[HTTP#DELETE]]

## Content Types
Related: [[HTTP#Content Types]]

### JSON
```bash
curl -X POST "https://api.example.com/data" \
  -H "Content-Type: application/json" \
  -d '{"key": "value"}'
```

### Form Data
```bash
curl -X POST "https://api.example.com/upload" \
  -F "file=@/path/to/file.pdf" \
  -F "description=My File"
```

### URL Encoded
```bash
curl -X POST "https://api.example.com/form" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  --data-urlencode "name=John Doe"
```

## Authentication

### Basic Auth
```bash
curl -u username:password https://api.example.com
```

### Bearer Token
```bash
curl -H "Authorization: Bearer token123" https://api.example.com
```

## Common Use Cases

### Download File
```bash
curl -o output.pdf https://example.com/file.pdf
```

### Follow Redirects
```bash
curl -L https://example.com
```

### Check HTTP Status
```bash
curl -I https://example.com
```

## Related
- [[HTTP]] - HTTP protocol details
- [[API]] - API documentation (if you have this note)
- [[REST]] - REST principles (if you have this note)