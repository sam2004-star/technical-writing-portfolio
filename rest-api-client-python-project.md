Request to Working Data — Creating a basic REST API client in Python is a guide to take a basic REST API and make it a working Python client.
Introduction

However, APIs are not deployed by themselves in real development. In most applications, they communicate with multiple endpoints, handle failure, process the data and present the data in a structured form.

In many cases the developer will write a tiny API client that will take care of this workflow instead of sending one request.

In this article, we will build a basic REST API client using python and demonstrate how to use APIs in a structured manner in real life problems.

1. Setting Up the API Call

We start with a simple setup for the request. In real projects, developers do not tend to create functions with no structure like this, but it's a good start.

import requests

api_url = "https://api.example.com/products"

try:
    response = requests.get(api_url)
    print("status:", response.status_code)
except Exception as e:
    print("something went wrong:", e)

Now we are only testing the reachability of the API and its response.

The third step is to add Basic Response Handling.The next step is Basic Response Handling (Step 3).

In real applications, you never know whether the API will be a success or not. Simple handling is added on top of this.

import requests

url = "https://api.example.com/products"

response = requests.get(url)

if response.status_code == 200:
    data = response.json()
    print("data received")
else:
    print("request failed:", response.status_code)

This is a first step towards a real API client.

Real Data Flow Collaborations

After receiving data from the API, we normally go through the data to gather useful information.

import requests

url = "https://api.example.com/products"
response = requests.get(url)

if response.status_code == 200:
    products = response.json()

    for p in products:
        name = p.get("name")
        print(name)
else:
    print("Error loading products")

The first phase would be for real developers to not want it to be too complicated, they would first verify the data and then improve the logic.

4. Handling Real-World Failures

APIs fail often. This should be performed by a competent client, and without crashes.

import requests

url = "https://api.example.com/products"

try:
    response = requests.get(url, timeout=5)

    if response.status_code == 200:
        products = response.json()

        for p in products:
            print("product:", p.get("name"))

    elif response.status_code == 404:
        print("endpoint not found")

    else:
        print("server returned:", response.status_code)

except Exception as err:
    print("network error:", err)

That's how REAL developers believe:

Assume that things can go wrong!
isolate network errors
handle responses differently

5. More Reusable Code

In real projects, logic of the requests is not duplicated throughout the project. Well, in the end, we put it into a simple function.

import requests

def fetch_products():
    url = "https://api.example.com/products"

    try:
        return requests.get(url, timeout=5)
    except:
        return None


res = fetch_products()

if res and res.status_code == 200:
    data = res.json()

    for item in data:
        print(item.get("name"))
else:
    print("Could not get data")

If the response from the server has "status_code": 200 and "res": "OK":
For each object in the res.json() array:
print(item["name"])
else:
print('Could not get data')

This is more resembling the structure of genuine API clients.

After that, what are the things that Real Developers improve?

If it was a production system, then developers would add:

This is a replacement of print statements with logging.Changes print to logging.
Try again logic - 100 fails
authentication headers
pagination handling
Your API URLs application configuration files.

Example idea:

headers = {
    "Authorization": "Bearer YOUR_TOKEN"
}
Conclusion

A REST API client isn't just a request, it's a client. It is a small system that deals with the communication, failure and data processing in an organized manner.

Understanding this flow can help developers create simple scripts to build robust, scalable applications.
