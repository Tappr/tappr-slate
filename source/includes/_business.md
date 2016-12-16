
# Businesses

## Business Create

> Request

```shell
curl -X POST "https://api.tappr.io/businesses" \
    -H "Authorization: Token eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ" \
    -d '{ }'
```

## Get all Businesses

> Request

```shell
curl -X GET "https://api.tappr.io/businesses" \
    -H "Authorization: Token eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ"
```

> Response

```json
    {
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
    }
```
