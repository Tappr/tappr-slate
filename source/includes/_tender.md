
# Tenders

## Tender Create

`TODO`

## Get all Tenders

> Request

```shell
curl -X GET "https://api.tappr.io/locations/:location_id/orders/:order_id/tenders" \
    -H "Authorization: Token eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ"
```

> Response

```json
[
    {
        "amount": {
            "currency_code": "AUD",
            "minor_units": 10000
        },
        "change": {
            "currency_code": "AUD",
            "minor_units": 0
        },
        "created_at": 1479433994,
        "device_id": "caf1e353-ebb9-4209-a7ef-e5bf0815b7da",
        "employee_id": "7e304336-74cc-49e6-b7d8-f1c59f4258c0",
        "id": "a608c9f6-4016-42e3-9596-b00979bd4f7c",
        "location_id": "711f4255-8d64-4ea9-993b-7e1fdf0971bb",
        "metadata": "{}",
        "order_id": "c953f762-112b-435a-b67d-9f5e2d0b8258",
        "payment_type": "CASH",
        "reference": "A757AC47-73ED-4359-B03D-072C897F0D09",
        "tendered": {
            "currency_code": "AUD",
            "minor_units": 0
        },
        "updated_at": 1479433994
    },
    {
        "amount": {
            "currency_code": "AUD",
            "minor_units": 255
        },
        "change": {
            "currency_code": "AUD",
            "minor_units": 0
        },
        "created_at": 1479343234,
        "device_id": "caf1e353-ebb9-4209-a7ef-e5bf0815b7da",
        "employee_id": "7e304336-74cc-49e6-b7d8-f1c59f4258c0",
        "id": "cd95e502-ade4-4f5e-90b2-e63d97fe5067",
        "location_id": "711f4255-8d64-4ea9-993b-7e1fdf0971bb",
        "metadata": "{}",
        "order_id": "d0dda653-a334-4a48-b08b-ff824315882d",
        "payment_type": "CASH",
        "reference": "06F43485-9032-4ADE-9686-B9C433FBAD27",
        "tendered": {
            "currency_code": "AUD",
            "minor_units": 0
        },
        "updated_at": 1479343234
    }
]
```

## Fields

| Field           | Description                                  |
|:----------------|:---------------------------------------------|
| `configuration` | Used to synchronize client specific settings |
