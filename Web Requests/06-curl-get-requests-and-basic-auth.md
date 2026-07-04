# cURL GET Requests and Basic Authentication

## Objective

Learn how to use cURL to interact with web applications that use HTTP Basic Authentication, inspect HTTP headers, and perform authenticated GET requests to retrieve protected resources.

---

# HTTP Basic Authentication

HTTP Basic Authentication is one of the simplest authentication mechanisms used by web servers. When a client attempts to access a protected resource, the server responds with a **401 Unauthorized** status and includes a `WWW-Authenticate` header.

Example response:

```http
HTTP/1.1 401 Unauthorized
WWW-Authenticate: Basic realm="Access denied"

The client must then provide a username and password encoded in Base64 using the Authorization header.

Accessing a Protected Resource

Attempting to access the application without authentication returns a 401 Unauthorized response.

curl -i http://<SERVER_IP>:<PORT>/

Example response:

HTTP/1.1 401 Unauthorized
WWW-Authenticate: Basic realm="Access denied"
Authenticating with cURL

The easiest way to authenticate is with the -u option.

curl -u admin:admin http://<SERVER_IP>:<PORT>/

If the credentials are correct, the server returns the protected page.

Authentication Using the URL

Basic Authentication credentials can also be supplied directly in the URL.

curl http://admin:admin@<SERVER_IP>:<PORT>/

Although this works, using the -u option is generally preferred.

Viewing the Authorization Header

Using the verbose option (-v) displays the complete HTTP request.

curl -v http://admin:admin@<SERVER_IP>:<PORT>/

Example request:

GET / HTTP/1.1
Host: <SERVER_IP>
Authorization: Basic YWRtaW46YWRtaW4=

The value after Basic is the Base64 encoding of:

admin:admin
Sending the Authorization Header Manually

Instead of using -u, the Authorization header can be added manually.

curl \
-H "Authorization: Basic YWRtaW46YWRtaW4=" \
http://<SERVER_IP>:<PORT>/

This produces the same authenticated request.

Discovering GET Requests

After authentication, the application provides a city search feature.

Using the browser's Developer Tools (Network tab), searching for a city reveals the following request:

GET /search.php?search=le

This indicates that the application uses a GET parameter named search.

Replaying the Request with cURL

The same request can be reproduced directly using cURL.

curl \
-H "Authorization: Basic YWRtaW46YWRtaW4=" \
"http://<SERVER_IP>:<PORT>/search.php?search=le"

Example response:

Leeds (UK)
Leicester (UK)
Browser Developer Tools

Developer Tools are extremely useful for web application testing.

The Network tab allows you to:

View every HTTP request
Inspect request headers
Inspect response headers
Copy requests as cURL
Identify GET and POST parameters

This information makes reproducing requests with cURL much easier.

HTB Lab Walkthrough
Step 1 — Authenticate

Login using the provided credentials.

Username:

admin

Password:

admin
Step 2 — Inspect the Search Request

Open the browser's Developer Tools.

Navigate to:

Network

Search for any city.

Observe the request:

/search.php?search=<value>
Step 3 — Replay the Request with cURL

Replace the search value with flag.

curl \
-H "Authorization: Basic YWRtaW46YWRtaW4=" \
"http://<SERVER_IP>:<PORT>/search.php?search=flag"
Step 4 — Retrieve the Flag

The response returns:

HTB{curl_g3773r}
Flag
HTB{curl_g3773r}
Key Takeaways
HTTP Basic Authentication uses the Authorization header.
The -u option in cURL automatically creates the required authentication header.
Protected resources return 401 Unauthorized until valid credentials are supplied.
Browser Developer Tools can reveal hidden API requests.
GET parameters can be modified and replayed directly with cURL.
Reproducing browser requests manually is a fundamental web penetration testing skill.
