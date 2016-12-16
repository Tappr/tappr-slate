
# Users

### Fields

| Field           | Description                                  |
|:----------------|:---------------------------------------------|
| `configuration` | Used to synchronize client specific settings |

## User Create

> Request

```shell
curl -X POST "https://api.tappr.io/user" \
    -d '{
            "email": "user@example.com",
            "first_name": "John",
            "last_name": "Smith",
            "pin": "1387"
        }'
```

## User Get

> Request

```shell
curl -X GET "https://api.tappr.io/user" \
    -H "Authorization: Token eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ"
```

> Response

```json
{
    "configuration": {},
    "created_at": 1479257221,
    "email": "example@tappr.io",
    "employments": [
        {
            "business": {
                "created_at": 1479257221,
                "currency_code": "AUD",
                "id": "cf3e762c-d19d-41f6-a396-b9f00999adbf",
                "locations": [
                    {
                        "address": {
                            "address_resolved": false,
                            "city": "Fortitude Valley",
                            "coordinates_resolved": false,
                            "line1": "1062 Ann Street",
                            "postcode": "4006",
                            "state": "QLD"
                        },
                        "created_at": 1479257221,
                        "id": "d152fd34-c884-4d91-a6d1-82a7685bb210",
                        "name": "Primary",
                        "phone_number": "1300TAPPR",
                        "status": "ACTIVE",
                        "timezone": "Australia/Brisbane",
                        "updated_at": 1479257221
                    }
                ],
                "mcc": "5735",
                "owner_id": "c7dae556-fee0-4e8e-9c94-0deea6a16fd6",
                "registered_name": "Tappr Pty Ltd",
                "trading_name": "Tappr",
                "updated_at": 1479257221,
                "use_trading_name": true
            },
            "created_at": 1479257221,
            "email": "example@tappr.io",
            "first_name": "Tappr",
            "id": "6c46a5fc-a41e-41b2-9fb3-9827162c4254",
            "last_name": "Developer",
            "status": "ACTIVE",
            "updated_at": 1479257221
        }
    ],
    "first_name": "Tappr",
    "id": "c7dae556-fee0-4e8e-9c94-0deea6a16fd6",
    "last_name": "Developer",
    "pin": "1111",
    "updated_at": 1479878939,
    "username": "example@tappr.io"
}
```
