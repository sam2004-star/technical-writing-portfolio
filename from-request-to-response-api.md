Introduction

When the developers are working on the API, it often appears as though it's: "Send a request, get a response. But it doesn't stop there, there's more involved with this simple interaction including client/server communication, data formatting and network protocols.

Understanding and knowing what happens between a request and a response is important to allow developers to debug, optimize performance and create better applications.

This article describes the entire life cycle of an API call, but in a step-by-step and easy-to-understand way.

How to use API Request?

API request – is a request made by a client (your application) asking for data or an action from the server.

Typical request includes:

Endpoint (URL)
The information contained in the message body (file contents).
Headers (metadata)
A body (optional) that is sent.

Example using Python:

import requests

url = "https://api.example.com/users"

try:
    response = requests.get(url)
    print("status:", response.status_code)
except Exception as e:
    print("request failed:", e)

In this case client is asking the server:

"Please tell me who is using the product.

What is the process after and when submit a request?

A bunch of stuff occurs in the background when they make the request:

Step 1: DNS Resolution

The domain name will be changed to an IP address by the browser or the application.

Example:

api.example.com → 192.168.1.10
Step 2: Make a Connection

The internet protocol (usually TCP) is used to initiate a connection between client and server.

Plus, there is a secure TLS handshake also if it's HTTPs.

The server accepts the request.

The server handles the request and passes it on to the right service or endpoint handler.

3. Server Processing

On receiving the request at the server, the server:

Validates the request
Checks the user's authentication (if required)
Ensures data consistency and integrity

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
5. Response to Client (RTC) – return the response to the client.

The server responds in the same path in the network.

It is forwarded to your app:

data = response.json()
print(data)

The data can be presented, stored or processed further at this stage.

7. Explains a list of typical HTTP status codes.

The status code will be included in each API response:

200 → Success
201 → Created
400 → Bad request
401 → Unauthorized
404 → Not found
500 → Server error

These codes are used to identify the events in the request/response cycle.

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

    for product in products:
        print(product["name"])
else:
    print("Request failed:", response.status_code)

This shows:

Request sent
Server processed it
Response returned
Data needed for the use of the app.

Conclusion

The entire API call process is not as straightforward as it sounds, with various steps such as resolving DNS, establishing a connection, coding the response from the server, and returning it in a structured manner.

When developers know this flow, it helps them:

Debug issues faster
Use Code in a more efficient way.
Build reliable applications
