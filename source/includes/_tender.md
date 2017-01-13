
# Tenders

## Tender Create

> Request

```shell
# curl -X POST "https://api.tappr.io/locations/:location_id/orders/:order_id/tenders" \
    -H "Authorization: Token eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ"
    -d '{
            "amount": {
                "currency_code": "AUD",
                "minor_units": 500
            },
            "change": {
                "currency_code": "AUD",
                "minor_units": 0
            },
            "device_id": "CAF1E353-EBB9-4209-A7EF-E5BF0815B7DA",
            "employee_id": "7e304336-74cc-49e6-b7d8-f1c59f4258c0",
            "payment_type": "CASH",
            "reference": "6978D003-C98B-424F-9DC3-66D0F86D356E",
            "tendered": {
                "currency_code": "AUD",
                "minor_units": 0
            }
        }'

```

### Fields

| Field              | Note       | Description                                                            |
|:-------------------|:-----------|:-----------------------------------------------------------------------|
| `amount`           |            | The amount given                                                       |
| `tendered`         |            | The amount taken (typically equivalent to amount for non cash tenders) |
| `change`           |            | The amount returned (typically zero for non cash tenders)              |
| `reference`        | `Optional` | An arbitrary id provided by the payment provider                       |
| `reference_source` | `Optional` | The source that provided the reference                                 |

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
    }
]
```


Get all transactions that match the specified filters. If no filter is specified it will fetch all transactions for the business since it started. We currently return 20 records at a time.

### Fields

|             |       |                                                             |
|:-------------------|:-----------|:-----------------------------------------------------------------------|
| `business_id`           |    `path`        | The unique id of the business.                                                      |
| `device_id`           |    `query`        | The serial number of the terminal allocated to the merchant.                                                      |
| `employee_id`           |    `query`        | The unique id of the employee.                                                     |
| `payment_type`           |    `query`        |                                                     |
| `card_scheme`           |    `query`        |                                                     |
| `card_account`           |    `query`        |                                                     |
| `pan_suffix`           |    `query`        |                                                     |
| `currency_code`           |    `query`        |                                                     
| `amount`           |            | The amount given                                                       |
| `tendered`         |            | The amount taken (typically equivalent to amount for non cash tenders) |
| `change`           |            | The amount returned (typically zero for non cash tenders)              |
| `reference`        | `Optional` | An arbitrary id provided by the payment provider                       |
| `reference_source` | `Optional` | The source that provided the reference                                 |


## Update Tender


## Get a Tender



