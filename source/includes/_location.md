
# Locations

## Location Create

> Request

```shell
curl -X POST "https://api.tappr.io/businesses/:business_id/locations" \
    -H "Authorization: Token eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ" \
    -d '{ }'
```

## Get all Locations

> Request

```shell
curl -X GET "https://api.tappr.io/business/:business_id/locations" \
    -H "Authorization: Token eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ"
```

> Response

```json
    [
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
    ]
```
