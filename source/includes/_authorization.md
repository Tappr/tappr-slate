# Authentication

## OAuth
The Tappr API Implements <a>OAuth 2.0</a> to allow users to log in to applications without exposing their credentials. The process involves several steps.

1. Acquire an access token, and optinoally a refresh token
2. Use the access token to make authenticated requests
3. If you were issued a refresh token: refresh the access token when it expires

<aside class="notice">To get started quicky, you can use the access token from the API playground and avoic implementing the OAuth login flow.</aside>

Before you begin, you need to create a client in the developer tools.

## Password Authentication

> Request

```shell
curl -X POST https://api.tappr.io/v1/authenticate \
  -H "Content-Type: application/json" \
  -d '{
        "client_id": "7ea20b0c-d163-4f4d-9fc5-62d56a151988",
        "grant_type": "password",
        "username": "john@example.com",
        "password": "wre2H2odwT96wactnn"
      }'
```

> Response

```json
{
    "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ",
    "refresh_token": "a171ab16c270a86be0dea1dcd2f36b0a"
}
```

Tappr's API expects an active API token to be included in request all authorized endpoints.

| Field       | Description                                                                   |
|:------------|:------------------------------------------------------------------------------|
| `client_id`   _REQUIRED_  | Issued to you when you register your application through `developer.tappr.io` |
| `grant_type`  _REQUIRED_  | Should be `password`, other grant type is `refresh_token`                     |
| `username`    _REQUIRED_  | user name of Tappr                                                            |
| `password`    _REQUIRED_  | password of Tappr                                                             |

## Refreshing Authentication

> Request

```shell
curl -X POST https://api.tappr.io/v1/authenticate \
  -H "application/json" \
  -d '{
        "client_id": "7ea20b0c-d163-4f4d-9fc5-62d56a151988",
        "grant_type": "refresh_token",
        "refresh_token": "a171ab16c270a86be0dea1dcd2f36b0a"
      }'
```

> Response

```json
{
    "access_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiI5NzY0NTU3ODA3NiIsIm5hbWUiOiJKb2huIERvZSIsImFkbWluIjp0cnVlfQ.g5XG4KXa3QYiJDEtBQwY0qnnvRnS8JbFDEl7ngUwT0A",
    "refresh_token": "7e0fb5bc8439833bcd5eab25c7004994"
}
```

When you receive an Access Token from the API through the `/authenticate` endpoint, you also receive a _Refresh Token_. This token may be used so continue your users session without prompting for their password again.

| Field       | Description                                                                   |
|:------------|:------------------------------------------------------------------------------|
| `client_id` _REQUIRED_      | Issued to you when you register your application through `developer.tappr.io` |
| `grant_type` _REQUIRED_     | should be `refresh_token`                                                     |
| `refresh_token` _REQUIRED_  | the value of _Refresh Token_ you got from password authentication          |
