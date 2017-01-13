
# Orders



```shell
GET / locations/{businessID}/orders
```

> Request

Orders represents a customer's request to purchase one or more items from a business. An order contains details about all the items or supplimentary sale requirements like discounts or fees. An order can be Open, Voided or Completed states. An active order will be in an Open state. 

### Arguements

| Field              | Note       | Description                                                 |
|:-------------------|:-----------|:------------------------------------------------------------|
| `business_id`            |      `path`      | String (Required)   |
| `if_modified_since`           | `header` | String (Optional)                          |
| `start_at`            | `query` | String (Optional)            |
| `end_at`        | `query` | String (Optional)                   |
| `limit`        | `query` | String (Optional)                        |
| `cardNumberFirst6`        | `Required` | String (Optional)                 |
| `cardNumberLast4` | `query` | String (Optional)                           |
| `cardExpirationMonth` | `query` | String (Optional)                    |
| `cardExpirationYear` | `query` | String (Optional)                    |
| `cardHolderFirstName` | `query` | String (Optional)                    |
| `cardHolderLastName` | `query` | String (Optional)                    |
| `store_id` | `query` | String (Optional)                    |
| `includesStaysAll` | `query` | Boolean (Optional)                    |


## Create Order

`POST / locations/{businessID}/orders`

### Fields

| Field              | Note       | Description                                                 |
|:-------------------|:-----------|:------------------------------------------------------------|
| `items`            |            | This field represents the goods provided through this order |
| `status`           | `Required` | [`OPEN` | `COMPLETED` | `VOIDED`]                           |
| `total`            | `Required` | This field *must* be the total displayed to a customer      |
| `opened_at`        | `Required` | The epoch timestamp the order was created at                |
| `opened_by`        | `Required` | The ID of the User that created the order                   |
| `reference`        | `Required` | An arbitrary id provided by the payment provider            |
| `reference_source` | `Required` | The source that provided the reference                      |

> Request

```shell
curl -X POST "https://api.tappr.io/locations/:location_id/orders" \
    -H "Authorization: Token eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ" \
    -d '{
            "items": [
                {
                    "discounts": [],
                    "fees": [],
                    "name": "Custom",
                    "price": {
                        "currency_code": "AUD",
                        "minor_units": 500
                    },
                    "quantity": 1.0,
                    "total": {
                        "currency_code": "AUD",
                        "minor_units": 500
                    },
                    "type": "CUSTOM"
                }
            ],
            "opened_at": 1481844679.02264,
            "opened_by": "7e304336-74cc-49e6-b7d8-f1c59f4258c0",
            "reference": "EC6D6350-E7CB-4169-AA24-1009D4ED4363",
            "reference_source": "TAPPR",
            "status": "COMPLETED",
            "tenders": [
                {
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
                }
            ],
            "total": {
                "currency_code": "AUD",
                "minor_units": 500
            }
        }'
```

## Get all Orders

Get all Orders that match specific filters. If no filter is specified it will fetch all order for the business since the business started. Tappr currently returns 20 records at a time. 


### ARGUEMENTS

| Field           |Type             | Description                        |
|:----------------|:----------------|:-------------------------------------|
| `business_id`    |`path` | string (required) |
| `if_modifed_since`    |`header` | string (optional) |
| `created_at`    |`query` | string (optional) |
| `ended_at`    |`query` | string (optional) |

> Request

```shell
curl -X GET "https://api.tappr.io/locations/:lid/orders" \
    -H "Authorization: Token eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ"
```

> Response

```json
[
    {
        "created_at": 1479433994,
        "id": "c953f762-112b-435a-b67d-9f5e2d0b8258",
        "items": [
            {
                "created_at": 1479433994,
                "name": "Custom",
                "price": {
                    "currency_code": "AUD",
                    "minor_units": 4000
                },
                "quantity": 1.0,
                "total": {
                    "currency_code": "AUD",
                    "minor_units": 4000
                },
                "type": "CUSTOM",
                "updated_at": 1479433994
            }
        ],
        "location_id": "711f4255-8d64-4ea9-993b-7e1fdf0971bb",
        "opened_at": "2016-11-18T01:53:00.000Z",
        "opened_by": "7e304336-74cc-49e6-b7d8-f1c59f4258c0",
        "reference": "005BA12F-31C9-47D8-A8B7-4BD1C2A48542",
        "reference_source": "TAPPR",
        "status": "COMPLETED",
        "tenders": [
            {
                "amount": {
                    "currency_code": "AUD",
                    "minor_units": 4000
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
        ],
        "total": {
            "currency_code": "AUD",
            "minor_units": 4000
        },
        "updated_at": 1479433994
    }
]
```

## Order Items

| Field      | Default  | Description                |
|:-----------|:---------|:---------------------------|
| `name`     | `Custom` | The name of the order item |
| `quantity` | `1.0`    | The quantity of units sold |
| `type`     |          | `[CUSTOM, PRODUCT]`        |

## Update an Order

## Cancel an Order
