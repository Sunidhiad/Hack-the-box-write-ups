cURL - GET Requests & Basic Authentication
Lab Information
Category	HTTP Requests
Topic	GET Requests, Basic Authentication, cURL
Difficulty	Easy
Goal	Authenticate using HTTP Basic Auth and retrieve the hidden flag using cURL
Objective
Authenticate using HTTP Basic Authentication
Inspect browser requests using Developer Tools
Recreate the request with cURL
Search for the keyword flag
Obtain the flag
Step 1 - Visit the Application

Open the target URL.

The page prompts for:

Username
Password

The credentials provided by the lab are:

Username: admin
Password: admin
Step 2 - Authenticate

Login using:

admin
admin

After authentication, the application displays a City Search feature.

Step 3 - Inspect the Request

Open browser Developer Tools.

F12

Go to:

Network

Clear previous requests.

Search for any city, for example:

le

A new request appears.

Example:

GET /search.php?search=le

The request contains:

Authorization: Basic YWRtaW46YWRtaW4=

which is the Base64 encoding of:

admin:admin
Step 4 - Copy the Request

Right-click the request.

Copy
→ Copy as cURL

The generated request is similar to:

curl 'http://IP:PORT/search.php?search=le' \
-H 'Authorization: Basic YWRtaW46YWRtaW4='
Step 5 - Search for the Flag

Replace the search value with:

flag

Command:

curl "http://IP:PORT/search.php?search=flag" \
-H "Authorization: Basic YWRtaW46YWRtaW4="
Step 6 - Retrieve the Flag

The server returns:

HTB{curl_g3773r}
Flag
HTB{curl_g3773r}
Key Concepts Learned
HTTP Basic Authentication
Authorization header
Base64 encoded credentials
Browser Developer Tools
Network request inspection
Copy as cURL
Sending authenticated GET requests
Using cURL to interact directly with web applications
Useful Commands

Authenticate using username/password:

curl -u admin:admin http://IP:PORT/

Authenticate using Authorization header:

curl -H "Authorization: Basic YWRtaW46YWRtaW4=" http://IP:PORT/

Search using GET parameter:

curl "http://IP:PORT/search.php?search=flag" \
-H "Authorization: Basic YWRtaW46YWRtaW4="
What I Learned
How HTTP Basic Authentication works.
How to inspect HTTP requests using browser Developer Tools.
How to identify GET parameters used by a web application.
How to recreate browser requests using cURL.
How to use the Authorization header to access protected resources.
How to retrieve hidden information by modifying GET parameter values.

This format matches a clean GitHub write-up style and fits well with your PortSwigger/HTB Academy notes repository.
