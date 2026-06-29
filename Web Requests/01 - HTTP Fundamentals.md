# HTB Academy Write-up: HyperText Transfer Protocol HTTP – cURL Download Exercise

## Lab Objective

The goal of this exercise was to use `cURL` to download or access the file returned by the `/download.php` endpoint on the target server and retrieve the flag.

## Target

```bash
154.57.164.82:30827
```

Endpoint:

```bash
/download.php
```

Full URL:

```bash
http://154.57.164.82:30827/download.php
```

## Concept Learned

HTTP is an application-level protocol used for communication between a client and a server. In this exercise, the client sends a request to the web server, and the server returns a resource.

`cURL` is a command-line tool used to send web requests. It is very useful for penetration testing because it allows us to interact with web servers directly from the terminal.

## Command Used

```bash
curl http://154.57.164.82:30827/download.php
```

## Explanation

The `curl` command sends an HTTP GET request to the given URL.

In this case:

```bash
curl http://154.57.164.82:30827/download.php
```

requested the file available at `/download.php`.

The server responded with the content of the file directly in the terminal.

## Mistake I Made

At first, I used:

```bash
curl -o http://154.57.164.82:30827/download.php
```

This caused an error because the `-o` option needs a filename after it.

Correct usage:

```bash
curl -o downloaded_file http://154.57.164.82:30827/download.php
```

or simply:

```bash
curl http://154.57.164.82:30827/download.php
```

## Flag

```text
HTB{64$!c_cURL_u$3r}
```

## Key Takeaways

* `curl URL` prints the server response in the terminal.
* `curl -o filename URL` saves the response into a custom file.
* `curl -O URL` saves the response using the remote filename.
* HTTP requests can be tested quickly using cURL without opening a browser.

## Final Answer

The flag was successfully retrieved using cURL:

```text
HTB{64$!c_cURL_u$3r}
```
