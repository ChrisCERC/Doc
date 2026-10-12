# WMS API definition
` [ Base URL: api.airtext.info/ ]

My API
API reference documentation
Property	Value
Version	1.0.0
Status	Stable
Base URL	https://api.example.com/v1
Content-Type	application/json
Table of Contents
Overview
Authentication
Endpoints
List users
Get user by ID
Create user
Data Models
Error Handling
Overview

This API allows clients to retrieve, create, and manage user resources.

Base URL
https://api.example.com/v1

Common Headers
Header	Value	Required
Authorization	Bearer <token>	Yes
Accept	application/json	No
Content-Type	application/json	For requests with a JSON body
Authentication

The API uses Bearer token authentication.

Include your access token in the Authorization header.

Authorization: Bearer <your-token>


Requests without a valid token may return 401 Unauthorized.

Endpoints
Users
1. List users

!GET

GET /users

Retrieve a paginated list of users.

Query Parameters
Parameter	Type	Required	Default	Description
page	integer	No	1	Page number
limit	integer	No	20	Number of results per page
Example Request
curl -X GET "https://api.example.com/v1/users?page=1&limit=20" \
  -H "Authorization: Bearer <your-token>" \
  -H "Accept: application/json"

Responses

200 OK — Request successful.

{
  "data": [
    {
      "id": 1,
      "name": "Jane Doe",
      "email": "jane@example.com"
    }
  ],
  "pagination": {
    "page": 1,
    "limit": 20,
    "total": 1
  }
}


Possible errors

Status	Description
401	Missing or invalid authentication
500	Internal server error
2. Get user by ID

!GET

GET /users/{id}

Retrieve a specific user using their unique ID.

Path Parameters
Parameter	Type	Required	Description
id	integer	Yes	Unique user identifier
Example Request
curl -X GET "https://api.example.com/v1/users/1" \
  -H "Authorization: Bearer <your-token>"

Responses

200 OK — User found.

{
  "id": 1,
  "name": "Jane Doe",
  "email": "jane@example.com"
}


Possible errors

Status	Description
401	Missing or invalid authentication
404	User not found
500	Internal server error
3. Create user

!POST

POST /users

Create a new user.

Request Body

Content-Type: application/json

Field	Type	Required	Description
name	string	Yes	User's full name
email	string	Yes	User's email address
Example Request
curl -X POST "https://api.example.com/v1/users" \
  -H "Authorization: Bearer <your-token>" \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Jane Doe",
    "email": "jane@example.com"
  }'

Responses

201 Created — User created successfully.

{
  "id": 2,
  "name": "Jane Doe",
  "email": "jane@example.com"
}


Possible errors

Status	Description
400	Invalid request body
401	Missing or invalid authentication
409	User already exists
500	Internal server error
Data Models
User

Represents a user resource.

Field	Type	Required	Description
id	integer	Yes	Unique user identifier
name	string	Yes	Full name
email	string	Yes	Email address
Example
{
  "id": 1,
  "name": "Jane Doe",
  "email": "jane@example.com"
}

Error Handling

Errors use a consistent JSON response format.

{
  "error": {
    "code": "USER_NOT_FOUND",
    "message": "The requested user could not be found."
  }
}

Common HTTP Status Codes
Status	Meaning	Description
200	OK	Request successful
201	Created	Resource created successfully
400	Bad Request	Invalid request parameters or body
401	Unauthorized	Authentication required or invalid
403	Forbidden	Insufficient permissions
404	Not Found	Resource does not exist
409	Conflict	Resource conflicts with existing data
500	Internal Server Error	Unexpected server error
Changelog
1.0.0
Initial API documentation.
Added user listing, retrieval, and creation examples.
