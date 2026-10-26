# HTTP Headers

HTTP headers provide additional information about an HTTP request or response. They consist of **name-value pairs** that communicate information such as content type, authentication credentials, and caching instructions.

Headers are separate from the request or response body.

## Request headers

Request headers are sent by the client (such as cURL, Postman, or a browser) to the server.

Common request headers include:

|Header|Description|Example|
|---|---|---|
|`Accept`|Specifies the response content types the client can accept.|`Accept: application/json`|
|`Content-Type`|Identifies the format of the request body.|`Content-Type: application/json`|
|`Authorization`|Provides credentials used to authenticate the request.|`Authorization: Bearer YOUR_TOKEN`|
|`User-Agent`|Identifies the client making the request.|`User-Agent: curl/8.0.1`|

### Example request

```http
POST /api/users HTTP/1.1
Host: api.example.com
Content-Type: application/json
Accept: application/json
Authorization: Bearer YOUR_TOKEN

{"name": "Alex"}
```

In this example:

- `Content-Type` tells the server that the request body contains JSON.
- `Accept` indicates that the client accepts JSON responses.
- `Authorization` supplies an authentication token.
- The JSON object is the **request body**, not a header.

## Response headers

Response headers are returned by the server and provide information about the response.

Common response headers include:

|Header|Description|Example|
|---|---|---|
|`Content-Type`|Identifies the format of the response body.|`Content-Type: application/json`|
|`Content-Length`|Indicates the size of the response body in bytes.|`Content-Length: 128`|
|`Cache-Control`|Specifies caching instructions.|`Cache-Control: no-cache`|
|`Location`|Identifies a URI associated with a redirect or newly created resource.|`Location: /api/users/123`|

### Example response

```http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 25

{"id":123,"name":"Alex"}
```

The response contains:

- **Status line:** `HTTP/1.1 200 OK`
- **Response headers:** `Content-Type` and `Content-Length`
- **Response body:** The JSON object

## `Content-Type` vs. `Accept`

These headers serve different purposes:

- **`Content-Type`** describes the format of the content being sent.
- **`Accept`** describes the response formats the client is willing to receive.

For example, a client can send JSON in a request and ask the server to return JSON in the response.

## Working with headers in cURL

Use `-H` to include a request header:

```bash
curl -H "Accept: application/json" https://api.example.com/users
```

Use `-i` to display response headers alongside the response body:

```bash
curl -i https://example.com
```

Use `-I` to request only the headers using the HTTP HEAD method:

```bash
curl -I https://example.com
```

See [[curl]] for additional commands and examples.

## HTTP headers in API documentation

When documenting an API endpoint, identify any headers that developers must include in their requests.

For each required header, document:

- **Name:** The exact header name.
- **Purpose:** What the header controls or communicates.
- **Required or optional:** Whether the request needs the header.
- **Expected value:** The format or accepted values.
- **Example:** How to include the header in a request.

For example:

|Header|Required|Description|
|---|---|---|
|`Authorization`|Yes|Bearer token used to authenticate the request.|
|`Content-Type`|Yes|Must be `application/json` when sending a JSON request body.|
|`Accept`|No|Set to `application/json` to request a JSON response.|

_These requirements are illustrative; actual header requirements depend on the API._

## Related notes

- [[curl]]