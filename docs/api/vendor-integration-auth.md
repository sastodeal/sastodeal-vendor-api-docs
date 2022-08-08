## Integration Login

`API Endpoint`: /api/auth/integration/login

`Method`: POST

**Request**

```json
{
    "username": "<integration_username>",
    "password": "<integration_password>",
    "session_name": "Integration test session"
}
```

**Response**

`HTTP_STATUS`: 200

```json
{
    "session_token": "<session_token>",
    "refresh_token": "<refresh_token>",
    "token": "<jwt_auth_token>"
}
```

* `token` need to be add as `Bearer` token for Authorization in each and evey request.

**Error Response**

`HTTP_STATUS`: 401

```json
{
    "code": 401,
    "message": "Expired JWT Token"
}
```

**Error Response**

`HTTP_STATUS`: 403

```json
{
  "title": "An error occurred",
  "status": 403,
  "detail": "You do not have permission to access this resource."
}
```
