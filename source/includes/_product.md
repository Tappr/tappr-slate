
# Products

Products are what a merchant sells at their business. Products have a `name`, `shotcode`, `sku`, and `price`. `sku` should be unique for tracking inventory. 


## Get List

```shell
GET /businesses/:business_id/products
```

## Product Create

> Request

```shell
curl -X POST "https://api.tappr.io/businesses/:business_id/products" \
    -H "Authorization: Token eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ"
    -d '{
            "name": "Flat-White",
            "variants": [
                {
                    "amount": {
                        "currency_code": "AUD",
                        "minor_units": 19999
                    },
                    "configuration": {},
                    "created_at": 1479344701,
                    "id": "730ebb67-9ec5-4013-898d-71a52ca780eb",
                    "updated_at": 1479344701
                }
            ]
        }'
```

### Fields

| Field      | Requirements |
|:-----------|:-------------|
| `variants` | `count > 0`  |


## Update Product

```shell
PUT /businesses/:business_id/products
```

## Categories

## Variants

Products may have 1 or more Variants. Variants represent different physical versions of a single product. Variants are where the price for the product is stored.

Typically this would be different sizes of the same product.




## Get all Products

> Request

```shell
curl -X GET "https://api.tappr.io/businesses/:business_id/products" \
    -H "Authorization: Token eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ"
```

> Response

```json
[
    {
        "categories": [],
        "configuration": {},
        "created_at": 1479344701,
        "id": "2edd62d6-58cf-426b-b5fe-b60d8b1cb45f",
        "name": "Red Herring",
        "status": "ACTIVE",
        "updated_at": 1479344701,
        "variants": [
            {
                "amount": {
                    "currency_code": "AUD",
                    "minor_units": 19999
                },
                "configuration": {},
                "created_at": 1479344701,
                "id": "730ebb67-9ec5-4013-898d-71a52ca780eb",
                "updated_at": 1479344701
            }
        ]
    }
]
```
