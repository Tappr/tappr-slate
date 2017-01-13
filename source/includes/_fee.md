
# Fees

Merchants must collect appropriate fees or "Taxes" based on their business and the products they sell. A fee, once defined, can be associated to a category, item or all tenders.


## Get Fee List
Get all fee rates for this merchant.

>Request 

```shell 
curl -X POST https://api.tappr.io/v1/businesses/:business_id/fees

```

###ARGUMENTS

| Field              | Note       | Description                                                 |
|:-------------------|:-----------|:------------------------------------------------------------|
| `if_modified_since`            |    `header`        | string (Optional) |
| `created_at`           | `query` | string (Optional)                           |
| `updated_at`            | `query` | string (Optional)     |
| `limit`        | `query` | integer (Optional)              |
| `business_id`        | `query` | string (Optional)                 |



## Create Fee

Create a fee rate definition for a business.

```shell 
curl -X POST https://api.tappr.io/v1/businesses/:business_id/fees

```

###ARGUMENTS

| Field              | Note       | Description                                                 |
|:-------------------|:-----------|:------------------------------------------------------------|
| `tax_id`        | `query` | string (Required)              |
| `business_id`        | `path` | string (Required)                 |

## Delete Fee

Delete a tax.

###ARGUMENTS

| Field              | Note       | Description                                                 |
|:-------------------|:-----------|:------------------------------------------------------------|
| `tax_id`        | `query` | string (Required)              |
| `business_id`        | `path` | string (Required)                 |

> Request

```shell
curl -X POST "https://api.tappr.io/businesses/:business_id/fees" \
    -H "Authorization: Token eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ"
    -d '{ }'

```



> Request

```shell
curl -X GET "https://api.tappr.io/businesses/:business_id/fees" \
    -H "Authorization: Token eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ"
```

> Response

```json
[ ]
```
