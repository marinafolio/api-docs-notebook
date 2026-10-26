# curl

curl (client URL) is a command-line tool for transferring data using URLs. It can send HTTP requests, retrieve responses, and interact with REST APIs without a browser.

## Common curl commands related to REST

| curl command        | Description                                                                                                                  | Example                                                              |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `-i` or `--include` | Includes the response headers in the response.                                                                               | `curl -i https://api.example.com/users`                              |
| `-I` or `--head`    | Sends a `HEAD` request to retrieve response headers without the response body.                                               | `curl -I https://api.example.com/users`                              |
| `-d` or `--data`    | Sends data in the request body. Commonly used with POST requests. The data format and appropriate headers depend on the API. | `curl -d "data-to-post" https://api.example.com/users`               |
| `-H` or `--header`  | Adds a request header, such as `Accept`, `Content-Type`, or `Authorization`.                                                 | `curl -H "Accept: application/json" https://api.example.com/users`   |
| `-X POST`           | Specifies the HTTP method to use with the request (in this example, `POST`).                                                 | `curl -X POST -d "resource-to-update" https://api.example.com/users` |
| `-d @filename`      | Reads request body data from a local file instead of entering it directly in the command.                                    | `curl -X POST -d @mypet.json https://api.example.com/users`          |

> [!tip]
> curl uses `GET` by default for ordinary requests. Using `-d` automatically makes the request a `POST` unless another method is specified.

## Viewing response headers

Use `-i` to display response headers alongside the response body:

```bash
curl -i https://api.example.com/users
```

Use `-I` to send a `HEAD` request and retrieve headers without the response body:

```bash
curl -I https://api.example.com/users
```

See [[HTTP Headers]] for an explanation of request and response headers.

## Sending JSON in a POST request

```bash
curl -X POST https://api.example.com/users \
  -H "Content-Type: application/json" \
  -d '{"name": "Alex"}'
```

- `-X POST` explicitly specifies the HTTP method (optional here because `-d` already selects POST).
- `-H "Content-Type: application/json"` tells the server that the request body contains JSON.
- `-d` supplies the JSON request body.

## Related notes

- [[HTTP Headers]]