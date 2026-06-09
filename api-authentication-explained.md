Introduction

When the developers are working on the API, it often appears as though it's: "Send a request, get a response. But it doesn't stop there, there's more involved with this simple interaction including client/server communication, data formatting and network protocols.

It's important to understand and know what happens between request and response so that the developers can understand, optimize the performance and build better applications.

This article describes the entire life cycle of an API call, but in a step-by-step and easy-to-understand way.

How to use API Request?

API request – is a request made by a client (your application) asking for data or an action from the server.

Typical request includes:

Endpoint (URL)
Any data in the message body (file contents).
Headers (metadata)
A body (optional) that is sent.

Example using Python:

import requests

url = "https://api.example.com/users"

try:
    response = requests.get(url)
    print("status:", response.status_code)
except: for any exception that isn't Exception:
    print("request failed:", e)

In this case client is asking the server:

Hey, let me know who's consuming the product?

What is the process after and when submit a request?

A bunch of stuff occurs in the background when they make the request:

Step 1: DNS Resolution

Browser or application will convert the domain name to an IP address.

Example:

api.example.com → 192.168.1.10
Step 2: Make a Connection

The internet protocol (usually TCP) is used to initiate a connection between client and server.

Plus, if it is HTTPs there is a secure TLS handshake as well.

The server accepts the request.

The server receives the request, and forwards it to the appropriate service or endpoint handler.

3. Server Processing

On receiving the request at the server, the server:

Validates the request
Validates user's authentication (if necessary)
Maintains consistency and integrity of data

Example:

SELECT * FROM users;
4. Creating the Response

Cooks up a response on the server after processing.

A response includes:

Status code (e.g., 200, 404, 500)
Headers
Data of the body usually in the JSON format.

Example response:

{
  "status": "success",
  "data": [
    {"id": 1, "name": "Alice"},
    {"id": 2, "name": "Bob"}
  ]
}
5. Response to Client (RTC) – send response to the client.

The server responds in the same path in the network.

It is passed on to your application:

data = response.json()
print(data)

At this point the data can be presented, stored or further processed.

7. Explains a list of typical HTTP status codes.

The status code will be included in each API response:

200 → Success
201 → Created
400 → Bad request
401 → Unauthorized
404 → Not found
500 → Server error

To identify the events in the request/response cycle, these codes are used.

This is because there are a number of different reasons why API Responses can fail, this being one of them.

Common reasons include:

Wrong endpoint URL
Missing authentication key
Server downtime
Invalid request format
Network issues

Example debugging step:

print(response.status_code)
print(response.text)
8. Real-World Example Flow

Let’s combine everything:

import requests

url = "https://api.example.com/products"

response = requests.get(url)

if response.status_code == 200:
    products = response.json()

    When a product is part of another product:
        print(product["name"])
else:
    print("Request failed:", response.status_code)

This shows:

Request sent
Server processed it
Response returned
Data needed for the use of the app.

Conclusion

All of the API call process isn't quite as simple as it sounds: everything that involves resolving DNS, establishing a connection, coding the response returned from the server and returning that response in a structured way.

Knowing this flow is helpful to developers when they:

Debug issues faster
Use Code in a more efficient way.
Build reliable applications
