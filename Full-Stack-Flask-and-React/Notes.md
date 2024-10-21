# Endpoint and payload anatomy

Endpoints - facilitate acess to resources on a server through routes or URLS.
* point at which data exchange occurs between two applications in a client-server environment.

Resource example venue
the venue represents an object or data structure accesible via a unique URL endpoint that allows
clients to retrieve, create, update, or delete information about the venue.

endpoint path for example
https://example.com:5000/api/v1/venues
    - https: Secured protocol
    - example.com: Domain name
    - 500: Port number
    - /api/v1/venues: Endpoint
    - /api/ represents the entry point of an API endpoint, /v1/ represents the version number of the API, and /venues 
    represents the resource.

# API opertaions
* Get /api/v1/venues: returns list of all venues
* Get /api/v1/venues/id: retrieves a single venue identified with id
* Post /api/v1/venues/: Creates a venue resource
* Update /api/v1/venues/id: Updates a single venue identified with id
* Delete /api/v1/venues/id: Deletes a single venue identified with id

Payloads - allow us to send data along with a request or a response.

example of a rexpected response in JSON format with get /api/v1/venues

[{

    "id": 1
    "name": "Auditorium A"
    },

    {
        "id":2
        "name": "Auditorium B"

    },

    ]

JSON response messages illustrate endpoint data representation based on the requests to the server.


# API endpoint best practices

* Use nouns as naming convention for an endpoint:
* Use plural nouns for collections.
* Adhere to the collection/resource/collection rule.


# Payload Structure
Example of a API request payload

POST /venues  HTTP/1.1Host: example.com
Accept: application/json
Content-Type: application/json
Content-Length: 10
{
"id":3
"name": "Conference Hall"
}

for the server-returned payload 
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 10
{"responseType": "OK",
"data": {"id":3
"name": "Conference Hall"
}}

* Note the payload consists of two key-value pairs: response type, and data type
* "responseType": "OK" indicates that the API successfully processed the request and returned a response "OK"
* "data": { "id": 3, "name": "Conference Hall" }: contains the actual data being returned by the API.
