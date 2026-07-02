# HTB Academy Write-up: HTTP Requests and Responses

## Objective

Understand how HTTP requests and responses work, how to inspect them using cURL, and how to identify useful information from response headers.

## Target

```bash
154.57.164.82:31923
```

## What is an HTTP Request?

An HTTP request is sent by the client, such as a browser or cURL, to the web server.

A basic HTTP request contains:

* Method
* Path
* HTTP version
* Headers
* Optional body

Example:

```http
GET / HTTP/1.1
Host: example.com
User-Agent: curl
Accept: */*
```

## What is an HTTP Response?

An HTTP response is sent by the server back to the client.

A response usually contains:

* HTTP version
* Status code
* Response headers
* Response body

Example:

```http
HTTP/1.1 200 OK
Server: Apache/2.4.41
Content-Type: text/html
```

## Command Used

To view the full request and response details, I used the verbose flag:

```bash
curl -v http://154.57.164.82:31923
```

## Finding the HTTP Method

While intercepting or inspecting the request, the HTTP method used was:

```text
GET
```

## Finding the Apache Version

In the response headers, the server revealed the Apache version:

```http
Server: Apache/2.4.41
```

So the answer was:

```text
2.4.41
```

## Key Takeaways

* HTTP communication happens through requests and responses.
* A request is sent by the client.
* A response is returned by the server.
* The `curl -v` command shows detailed request and response information.
* Response headers can reveal useful information such as server type and version.
* Server version disclosure can be useful during reconnaissance.

## Final Answers

Question 1:

```text
GET
```

Question 2:

```text
2.4.41
```
