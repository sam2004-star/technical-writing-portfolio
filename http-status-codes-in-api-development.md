Knowledge of the different status codes that are utilized in the API.
Introduction

APIs will respond with a response to each request made. The server also sends a number, called the HTTP status code.

These status codes are crucial to help understand what has happened in a request. The status code will be the best indicator of a success, failure or redirect request.

This article will discuss the most important HTTP status codes and how to use them in building a real-world API.

2. What is a status code?3. What do each of the status codes indicate?

HTTP status codes are standardized numbers which are returned by a server in response to a request from a client.

This allows them to be able to return the outcome of the request without having to read the entirety of the response body.

Example:

import requests

url = "https://api.example.com/users"

response = requests.get(url)

print("status code:", response.status_code)

There are the following type of status codes:

There are five classes of HTTP status codes:

1xx — Informational

Request received – processing will continue.

2xx — Success

Processing the request was successful.

3xx — Redirection

There is a request but there's more work to go with it.

4xx — Client Errors

There was an error in the request.

5xx — Server Errors

The server didn't accept the request.

The most common status codes.
200 — OK

Request was successful.

import requests

response = requests.get("https://api.example.com/data")

if response.status_code == 200:
    data = response.json()
    print("Success:", data)
201 — Created

A new resource was successfully created.

400 — Bad Request

An invalid or malformed request was made.

response = requests.get("https://api.example.com/bad-endpoint")

print("status:", response.status_code)
401 — Unauthorized

No user was provided nor any incorrect credentials were provided.

404 — Not Found

We were not able to find the requested resource.

500 — Internal Server Error

There was a problem on the server.

The 4th part is where Developers use Status Codes.

By using status codes the developers control application logic.

Example:

import requests

response = requests.get("https://api.example.com/products")

if response.status_code == 200:
    data = response.json()

    for item in data:
        print("product:", item["name"])

elif response.status_code == 404:
    print("Resource not found")

else:
    print("Unexpected error:", response.status_code)
5. Status Codes are important.

The significance of status codes is that they:

Make the debugging of APIs simpler and quicker.Debug APIs more easily and quickly.
Apply more robust error handling to applications
Ensure that systems are more reliable
Filter the information between client and server so that it is easy to understand.

Conclusion

HTTP status codes are a part of API communication. Once developers have the understanding of such concepts, they can more accurately interpret the signals and design better systems.

Understanding status codes is an important step towards building the confidence of making API's and debugging.
