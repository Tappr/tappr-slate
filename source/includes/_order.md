
# Orders

## Order Create

`TODO`

## Get all Orders

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
                    "minor_units": 3500
                },
                "quantity": 1.0,
                "total": {
                    "currency_code": "AUD",
                    "minor_units": 3500
                },
                "type": "CUSTOM",
                "updated_at": 1479433994
            },
            {
                "created_at": 1479433994,
                "name": "Custom",
                "price": {
                    "currency_code": "AUD",
                    "minor_units": 2500
                },
                "quantity": 1.0,
                "total": {
                    "currency_code": "AUD",
                    "minor_units": 2500
                },
                "type": "CUSTOM",
                "updated_at": 1479433994
            },
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
        ],
        "total": {
            "currency_code": "AUD",
            "minor_units": 10000
        },
        "updated_at": 1479433994
    },
    {
        "created_at": 1479688490,
        "id": "4407b4de-3067-4804-b2a2-ab5d6970cabb",
        "items": [
            {
                "created_at": 1479688490,
                "name": "Red Herring",
                "price": {
                    "currency_code": "AUD",
                    "minor_units": 19999
                },
                "product_reference": "",
                "quantity": 1.0,
                "source": "TAPPR",
                "total": {
                    "currency_code": "AUD",
                    "minor_units": 19999
                },
                "type": "PRODUCT",
                "updated_at": 1479688490,
                "variant_reference": ""
            }
        ],
        "location_id": "711f4255-8d64-4ea9-993b-7e1fdf0971bb",
        "opened_at": "2016-11-21T00:34:07.000Z",
        "opened_by": "7e304336-74cc-49e6-b7d8-f1c59f4258c0",
        "reference": "0251095A-BD80-41ED-AD14-1743134696EA",
        "reference_source": "TAPPR",
        "status": "COMPLETED",
        "tenders": [
            {
                "amount": {
                    "currency_code": "AUD",
                    "minor_units": 19999
                },
                "change": {
                    "currency_code": "AUD",
                    "minor_units": 0
                },
                "created_at": 1479688490,
                "device_id": "caf1e353-ebb9-4209-a7ef-e5bf0815b7da",
                "employee_id": "7e304336-74cc-49e6-b7d8-f1c59f4258c0",
                "id": "533c843e-4558-4986-9c0a-e50be042afe8",
                "location_id": "711f4255-8d64-4ea9-993b-7e1fdf0971bb",
                "metadata": "{}",
                "order_id": "4407b4de-3067-4804-b2a2-ab5d6970cabb",
                "payment_type": "CASH",
                "reference": "4E0842D6-60F5-4D12-A09B-7A4046433A58",
                "tendered": {
                    "currency_code": "AUD",
                    "minor_units": 0
                },
                "updated_at": 1479688490
            }
        ],
        "total": {
            "currency_code": "AUD",
            "minor_units": 19999
        },
        "updated_at": 1479688490
    },
    {
        "created_at": 1479343234,
        "id": "d0dda653-a334-4a48-b08b-ff824315882d",
        "items": [
            {
                "created_at": 1479343234,
                "name": "Custom",
                "price": {
                    "currency_code": "AUD",
                    "minor_units": 255
                },
                "quantity": 1.0,
                "total": {
                    "currency_code": "AUD",
                    "minor_units": 255
                },
                "type": "CUSTOM",
                "updated_at": 1479343234
            }
        ],
        "location_id": "711f4255-8d64-4ea9-993b-7e1fdf0971bb",
        "opened_at": "2016-11-17T00:40:29.000Z",
        "opened_by": "7e304336-74cc-49e6-b7d8-f1c59f4258c0",
        "reference": "04C1586B-4327-46C3-9E56-1D0ECD01BC59",
        "reference_source": "TAPPR",
        "status": "COMPLETED",
        "tenders": [
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
        ],
        "total": {
            "currency_code": "AUD",
            "minor_units": 255
        },
        "updated_at": 1479343234
    }
]
```

## Fields

| Field         | Description                             |
|:--------------|:----------------------------------------|
| `order_items` | The items included in this order        |
| `tenders`     | The tenders recorded against this order |

## OrderItems

| Field      | Default  | Description                |
|:-----------|:---------|:---------------------------|
| `name`     | `Custom` | The name of the order item |
| `quantity` | `1.0`    | The quantity of units sold |
| `type`     |          | `[CUSTOM, PRODUCT]`        |
