cURL - POST Requests & Session Cookies
Lab Information
Category	HTTP Requests
Topic	POST Requests, Session Cookies, JSON Requests
Difficulty	Easy
Goal	Authenticate, capture the session cookie, and use it to send an authenticated JSON POST request with cURL
Objective
Authenticate using a login form
Capture the session cookie
Reuse the cookie with cURL
Send a JSON POST request
Retrieve the hidden flag
Step 1 - Visit the Application

Browse to the target application.

The login page contains:

Username
Password
Login button

Use the provided credentials:

Username: admin
Password: admin
Step 2 - Inspect the Login Request

Open Developer Tools.

F12

Navigate to:

Network

Login using:

admin
admin

A POST request is sent to the server.

Request body:

username=admin&password=admin
Step 3 - Authenticate Using cURL

Replicate the login request.

curl -X POST \
-d "username=admin&password=admin" \
http://IP:PORT/

The response returns the authenticated page.

Step 4 - Capture the Session Cookie

Display the response headers.

curl -i -X POST \
-d "username=admin&password=admin" \
http://IP:PORT/

Example response:

HTTP/1.1 200 OK

Set-Cookie: PHPSESSID=c1nsa6op7vtk7kdis7bcnbadf1

The important value is:

PHPSESSID=<session_id>
Step 5 - Reuse the Session Cookie

Use the authenticated session cookie with cURL.

curl -b "PHPSESSID=<session_id>" \
http://IP:PORT/

Instead of the login page, the application returns the authenticated search page.

Step 6 - Inspect the Search Request

Search for any city.

Example:

London

Developer Tools shows a POST request sent to:

/search.php

Request body:

{"search":"London"}

Request header:

Content-Type: application/json
Step 7 - Search for the Flag

Replace the search value with:

flag

Send the request using the authenticated cookie.

curl -X POST \
-b "PHPSESSID=<session_id>" \
-H "Content-Type: application/json" \
-d '{"search":"flag"}' \
http://IP:PORT/search.php
Step 8 - Retrieve the Flag

The application returns:

HTB{p0$t_r3p34t3r}
Flag
HTB{p0$t_r3p34t3r}
Key Concepts Learned
HTTP POST requests
Form-based authentication
Session management using cookies
Set-Cookie response header
Sending cookies with cURL
JSON request bodies
Content-Type: application/json
Interacting directly with backend endpoints
Useful Commands
Login
curl -X POST \
-d "username=admin&password=admin" \
http://IP:PORT/
View Response Headers
curl -i -X POST \
-d "username=admin&password=admin" \
http://IP:PORT/
Access Using Session Cookie
curl -b "PHPSESSID=<session_id>" \
http://IP:PORT/
Send JSON POST Request
curl -X POST \
-b "PHPSESSID=<session_id>" \
-H "Content-Type: application/json" \
-d '{"search":"flag"}' \
http://IP:PORT/search.php
What I Learned
How web applications authenticate users using POST requests.
How to inspect login requests with Developer Tools.
How to extract and reuse session cookies.
How authenticated sessions are maintained using PHPSESSID.
How to send JSON data using cURL.
How to communicate directly with backend endpoints without using the web interface.
How to combine cookies and JSON requests to access protected functionality and retrieve hidden data.

