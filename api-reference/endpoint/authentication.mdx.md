---
title: 'Authentication'
description: 'Endpoints for user authentication and authorization'
---

# Authentication

This section covers the endpoints used for user authentication and authorization.

## Login

Authenticate a user and receive a JWT token.

### Request

```http
POST /login
Content-Type: application/json

{
  "username": "string",
  "password": "string",
  "redirect": "string"
}
```

### Response

```json
{
  "message": "Login successful",
  "user": {
    "id": "string",
    "username": "string",
    "roles": ["string"]
  },
  "token": "string"
}
```

## Check Authentication

Verify the authentication status of a user.

### Request

```http
POST /check-auth
Content-Type: application/json

{
  "token": "string"
}
```

### Response

```json
{
  "isAuthenticated": true,
  "employee": {
    "_id": "string",
    "username": "string",
    "role": ["string"]
  }
}
```

Both endpoints will return appropriate error responses for invalid credentials or tokens.
