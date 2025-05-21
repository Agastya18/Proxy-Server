# HTTP Proxy Server

A simple HTTP proxy server with caching capabilities implemented in C.

## Overview

This proxy server acts as an intermediary between clients and web servers. It accepts HTTP requests from clients, forwards them to the appropriate web servers, and returns the responses back to the clients. Additionally, it implements a caching mechanism to improve performance for repeated requests.

## Features

- HTTP request parsing and forwarding
- Response caching for improved performance
- Thread-based handling of multiple concurrent clients
- Error handling with appropriate HTTP status codes
- Support for HTTP/1.0 and HTTP/1.1

## Building the Proxy

To build the proxy server, simply run:

```
make
```

This will compile the source files and create the executable `proxy`.

## Running the Proxy

To start the proxy server, run:

```
./proxy <port_number>
```

Where `<port_number>` is the port on which the proxy server will listen for incoming connections.

## Implementation Details

The proxy server consists of the following components:

- `proxy_server_with_cache.c`: Main implementation with caching functionality
- `proxy_parse.c` and `proxy_parse.h`: HTTP request parsing library
- `Makefile`: Build configuration

### Caching Mechanism

The proxy implements an LRU (Least Recently Used) caching strategy to store and retrieve previously requested resources. This reduces load on origin servers and improves response times for frequently accessed content.

### Error Handling

The proxy handles various error conditions and returns appropriate HTTP status codes:
- 400 Bad Request
- 403 Forbidden
- 404 Not Found
- 500 Internal Server Error
- 501 Not Implemented
- 505 HTTP Version Not Supported

##### OS Component Used ​
- Threading
- Locks 
- Semaphore
- Cache (LRU algorithm is used in it)

## How to Run

```bash
$ git clone https://github.com/Agastya18/Proxy-Server.git
$ cd MultiThreadedProxyServerClient
$ make all
$ ./proxy <port no.>
```
`Open http://localhost:port/https://www.cs.princeton.edu/`

## Limitations

- Only supports the HTTP GET method
- Limited to HTTP (not HTTPS)
- Basic caching implementation

## License

This project is provided as-is for educational purposes.