
# Authentication

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

## Fields

| Field       | Description                                                                 |
|:------------|:----------------------------------------------------------------------------|
| `client_id` | Issued to you when you register your application through developer.tappr.io |
