CRUD API
🎯 Objective

Learn how to interact directly with a REST-style API using cURL and perform all four CRUD operations:

Create (POST)
Read (GET)
Update (PUT)
Delete (DELETE)

Finally, manipulate the API to retrieve the hidden flag.

Skills Learned
Using cURL with REST APIs
Reading JSON responses
Formatting JSON using jq
Sending JSON request bodies
Using HTTP methods:
GET
POST
PUT
DELETE
Modifying API resources
Understanding CRUD
Operation	HTTP Method	Purpose
Create	POST	Add new data
Read	GET	Retrieve data
Update	PUT	Modify existing data
Delete	DELETE	Remove data
Reading API Data (GET)

Retrieve information about a city.

curl http://<SERVER_IP>:<PORT>/api.php/city/london

Pretty-print JSON output:

curl -s http://<SERVER_IP>:<PORT>/api.php/city/london | jq

Example output:

[
  {
    "city_name": "London",
    "country_name": "(UK)"
  }
]

Retrieve all cities:

curl -s http://<SERVER_IP>:<PORT>/api.php/city/ | jq
Creating a New City (POST)

Add a new record to the database.

curl -X POST \
http://<SERVER_IP>:<PORT>/api.php/city/ \
-d '{"city_name":"HTB_City","country_name":"HTB"}' \
-H "Content-Type: application/json"

Verify:

curl -s http://<SERVER_IP>:<PORT>/api.php/city/HTB_City | jq
Updating Existing Data (PUT)

Modify an existing city.

Example:

curl -X PUT \
http://<SERVER_IP>:<PORT>/api.php/city/london \
-d '{"city_name":"New_HTB_City","country_name":"HTB"}' \
-H "Content-Type: application/json"

Verify:

curl -s http://<SERVER_IP>:<PORT>/api.php/city/New_HTB_City | jq
Deleting Data (DELETE)

Remove an entry.

curl -X DELETE \
http://<SERVER_IP>:<PORT>/api.php/city/New_HTB_City

Verify deletion:

curl -s http://<SERVER_IP>:<PORT>/api.php/city/New_HTB_City | jq

Expected output:

[]
Lab Walkthrough
Step 1 — Update Any City to flag

Choose an existing city (for example, London).

curl -X PUT \
http://<SERVER_IP>:<PORT>/api.php/city/london \
-d '{"city_name":"flag","country_name":"HTB"}' \
-H "Content-Type: application/json"
Step 2 — Delete Any City

Delete another city.

Example:

curl -X DELETE \
http://<SERVER_IP>:<PORT>/api.php/city/leeds
Step 3 — Search for flag
curl -s http://<SERVER_IP>:<PORT>/api.php/city/flag | jq

The response contains the flag.

HTB{crud_4p!_m4n!pul4t0r}
Flag
HTB{crud_4p!_m4n!pul4t0r}
Key Takeaways
APIs commonly expose CRUD functionality through HTTP methods.
GET retrieves resources.
POST creates new records.
PUT modifies existing records.
DELETE removes records.
JSON APIs require the Content-Type: application/json header.
jq makes JSON responses easier to read.
cURL is a powerful tool for interacting directly with APIs without using the web interface.
