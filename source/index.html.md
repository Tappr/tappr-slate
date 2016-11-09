---
title: API Reference

language_tabs:
  - shell


toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction


<aside class="notice">Tappr API doc. This is a WORKING copy and will change.</aside>

# Authentication

```shell
curl -X POST "http://localhost:3000/v1/authenticate" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Content-Type** should respect the following schema:

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```
> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{\"client_id\":\"7e6ebd1e-1c5e-4db8-a6be-6379c8d99f17\",\"grant_type\":\"password\",\"username\":\"daniel@mytappr.com\",\"password\":\"Password123\"}"
}
```

# User Create

```shell
curl -X POST "http://localhost:3000/v1/user" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Content-Type** should respect the following schema:

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{\"first_name\":\"Daniel\",\"last_name\":\"Draper\",\"email\":\"daniel@mytappr.com\",\"username\":\"daniel@mytappr.com\",\"password\":\"Password123\"}"
}
```

# Get User

```shell
curl -X GET "http://localhost:3000/v1/user" \
    -H "Authorization: $Authorization"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

# Create Business

```shell
curl -X POST "http://localhost:3000/v1/businesses" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```


```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{\"registered_name\":\"Tappr Pty Ltd\",\"phone_number\":\"0732457832\",\"address\":{\"line1\":\"Level 2, 1062 Ann Street\",\"city\":\"Fortitude Valley\",\"state\":\"Queensland\",\"postcode\":\"4006\",\"country_code\":\"AU\"},\"mcc\":\"4100\",\"currency_code\":\"AUD\",\"timezone\":\"Australia/Brisbane\"}"
}
```

# Get Business

```shell
curl -X GET "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304" \
    -H "Authorization: $Authorization"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

# Update Business

```shell
curl -X PUT "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{\"use_trading_name\":true,\"trading_name\":\"Tappr\"}"
}
```

# Get Businesses

```shell
curl -X GET "http://localhost:3000/v1/businesses" \
    -H "Authorization: $Authorization"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

# Create Fees

```shell
curl -X POST "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/fees" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{\"name\":\"GST\",\"status\":\"ACTIVE\",\"apply_to_custom_amount\":true,\"fee_type\":\"GOVERNMENT\",\"inclusion_type\":\"ADDITIVE\",\"calculation_phase\":\"TOTAL\",\"amount\":{\"minor_units\":10,\"currency_code\":\"AUD\"}}"
}
```

# Get Fee

```shell
curl -X GET "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/fees/730f43f0-c76e-4d87-b1f9-5a8a2106528d" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{}"
}
```

# Update Fees

```shell
curl -X PUT "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/fees/730f43f0-c76e-4d87-b1f9-5a8a2106528d" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{\"name\":\"Goods and Services Tax (GST)\",\"rate\":0.1}"
}
```

# Get Fees

```shell
curl -X GET "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/fees" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{}"
}
```

# Create Order Modifiers

```shell
curl -X POST "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/modifiers" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{\"name\":\"Milk\",\"min_selection\":\"1\",\"max_selection\":\"1\",\"status\":\"ACTIVE\",\"options\":[{\"name\":\"Full Cream\",\"is_default\":true,\"status\":\"ACTIVE\",\"amount\":{\"minor_units\":100,\"currency_code\":\"AUD\"}}]}"
}
```

# Update Order Modifiers

```shell
curl -X PUT "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/modifiers/35cc18bc-d35b-4fc5-ab30-00b81f888925" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{\"name\":\"Mulk\",\"options\":[{\"id\":\"01f872ad-528b-4b7b-8183-1fb3fe619c0e\",\"name\":\"Cow Juice\"}]}"
}
```

# Get Modifier

```shell
curl -X GET "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/modifiers/35cc18bc-d35b-4fc5-ab30-00b81f888925" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{}"
}
```

# Get Modifiers

```shell
curl -X GET "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/modifiers" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{}"
}
```

# Delete Modifier

```shell
curl -X DELETE "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/modifiers/48a36d70-2f50-4121-9c85-9de756cbda28" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{}"
}
```

# Create Categories

```shell
curl -X POST "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/categories" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{\"name\":\"Beverages\"}"
}
```

# Get Category

```shell
curl -X GET "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/categories/969b96b0-7686-424a-8678-ab024c923b8b" \
    -H "Authorization: $Authorization"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

# Update Category

```shell
curl -X PUT "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/categories/0afa10da-d961-4a90-be6e-6bac4ce1cb2b" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{\"name\":\"Drinks\"}"
}
```

# Delete Category

```shell
curl -X DELETE "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/categories/0afa10da-d961-4a90-be6e-6bac4ce1cb2b" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{}"
}
```

# Get Categories

```shell
curl -X GET "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/categories" \
    -H "Authorization: $Authorization"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

# Get Products

```shell
curl -X GET "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/products" \
    -H "Authorization: $Authorization"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

# Create Product

```shell
curl -X POST "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/products" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```


```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{\"name\":\"Bondi Chai Latt\\u00e8\",\"description\":\"Bondi Chai is the Gold Standard in chai latte. A silk-smooth creaminess and 'almost addictive' tastemake Bondi Chai one of Australia's favourite drinks, enhancing the best moments of every day.\",\"variants\":[{\"name\":\"Small\",\"sku\":\"CHAI-SM-0001\",\"amount\":{\"minor_units\":200,\"currency_code\":\"AUD\"}},{\"name\":\"Medium\",\"sku\":\"CHAI-MD-0001\",\"amount\":{\"minor_units\":300,\"currency_code\":\"AUD\"}},{\"name\":\"Large\",\"sku\":\"CHAI-LG-0001\",\"amount\":{\"minor_units\":400,\"currency_code\":\"AUD\"}}],\"category_ids\":[\"0e12eebf-ab9c-4caa-974b-0218c19184f0\"]}"
}
```

# Update Product

```shell
curl -X PUT "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/products/0cbe4b7f-4ec4-4eda-92c8-0f42119c03e1" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{\"name\":\"Latt\\u00e8\",\"description\":\"A silk-smooth creaminess and 'almost addictive' tastemake chai one of Australia's favourite drinks, enhancing the best moments of every day.\"}"
}
```

# Get Product

```shell
curl -X GET "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/products/0cbe4b7f-4ec4-4eda-92c8-0f42119c03e1" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{}"
}
```

# Delete Product

```shell
curl -X DELETE "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/products/0cbe4b7f-4ec4-4eda-92c8-0f42119c03e1" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{}"
}
```

# Get Business Locations

```shell
curl -X GET "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/locations" \
    -H "Authorization: $Authorization"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

# Get Business Location

```shell
curl -X GET "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/locations/6f161162-b3a5-446e-b5ed-de9ca93fe003" \
    -H "Authorization: $Authorization"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

# Update Business Locatoion

```shell
curl -X PUT "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/locations/6f161162-b3a5-446e-b5ed-de9ca93fe003" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{\"name\":\"Tappr HQ\"}"
}
```

# Create Business Location

```shell
curl -X POST "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/locations" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{\"name\":\"Tappr\",\"phone_number\":\"0732457856\",\"status\":\"ACTIVE\",\"address\":{\"line1\":\"Level 2, 1062 Ann Street\",\"city\":\"Fortitude Valley\",\"state\":\"Queensland\",\"postcode\":\"4006\",\"country_code\":\"AU\",\"coordinates_resolved\":false,\"address_resolved\":false},\"timezone\":\"Australia/Brisbane\"}"
}
```

# Create Discount

```shell
curl -X POST "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/discounts" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{\"name\":\"Emergency Services Discount\",\"description\":\"This discount can be applied to emergency services personnel.\",\"status\":\"ACTIVE\",\"rate\":\"0.20\"}"
}
```

# Get Discount

```shell
curl -X GET "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/discounts/79a2477e-dda8-421f-b2ad-d2a67c6d21b8" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{}"
}
```

# Get Discounts

```shell
curl -X GET "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/discounts" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{}"
}
```

# Update Discount

```shell
curl -X PUT "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/discounts/79a2477e-dda8-421f-b2ad-d2a67c6d21b8" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{\"name\":\"Emergency Responder Discount\",\"amount\":{\"minor_units\":100,\"currency_code\":\"AUD\"}}"
}
```

# Delete Discount

```shell
curl -X DELETE "http://localhost:3000/v1/businesses/0d36feb6-ced5-4f03-97ad-209763150304/discounts/79a2477e-dda8-421f-b2ad-d2a67c6d21b8" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{}"
}
```

# Get Orders

```shell
curl -X GET "http://localhost:3000/v1/locations/d3a893ac-6724-457c-8770-1a8b48748880/orders" \
    -H "Authorization: $Authorization"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

# Create Order

```shell
curl -X POST "http://localhost:3000/v1/locations/d3a893ac-6724-457c-8770-1a8b48748880/orders" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```

```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{\"status\":\"OPEN\",\"reference\":\"\",\"reference_source\":\"Tappr\",\"opened_at\":\"1476077339\",\"opened_by\":\"e04f9573-4a63-41aa-95f1-a3e224e14384\",\"items\":[{\"type\":\"CUSTOM\",\"name\":\"Custom\",\"quantity\":2,\"price\":{\"minor_units\":2000,\"currency_code\":\"AUD\"},\"total\":{\"minor_units\":4000,\"currency_code\":\"AUD\"}},{\"type\":\"PRODUCT\",\"name\":\"Latt\\u00e8\",\"variant_name\":\"Large\",\"source\":\"Tappr\",\"product_reference\":\"\",\"variant_reference\":\"\",\"quantity\":2,\"price\":{\"minor_units\":450,\"currency_code\":\"AUD\"},\"total\":{\"minor_units\":1030,\"currency_code\":\"AUD\"},\"modifiers\":[{\"reference\":\"\",\"name\":\"Milk\",\"total\":{\"minor_units\":30,\"currency_code\":\"AUD\"},\"options\":[{\"reference\":\"\",\"name\":\"Soy\",\"quantity\":1,\"price\":{\"minor_units\":30,\"currency_code\":\"AUD\"},\"total\":{\"minor_units\":30,\"currency_code\":\"AUD\"}}]},{\"reference\":\"\",\"name\":\"Syrup\",\"total\":{\"minor_units\":100,\"currency_code\":\"AUD\"},\"options\":[{\"reference\":\"\",\"name\":\"Caramel\",\"quantity\":2,\"price\":{\"minor_units\":50,\"currency_code\":\"AUD\"},\"total\":{\"minor_units\":100,\"currency_code\":\"AUD\"}}]}]}],\"total\":{\"minor_units\":850,\"currency_code\":\"AUD\"},\"tenders\":[{\"device_id\":\"\",\"employee_id\":\"e04f9573-4a63-41aa-95f1-a3e224e14384\",\"payment_type\":\"CASH\",\"amount\":{\"minor_units\":1000,\"currency_code\":\"AUD\"},\"tendered\":{\"minor_units\":1000,\"currency_code\":\"AUD\"},\"change\":{\"minor_units\":0,\"currency_code\":\"AUD\"},\"reference\":\"\"}]}"
}
```

# Create Reciept

```shell
curl -X POST "http://localhost:3000/v1/locations/d3a893ac-6724-457c-8770-1a8b48748880/orders/f99e75cf-0be6-42ed-8246-b55aa894f7a8/tenders/9f912329-0416-4d20-acab-dbf33f32a8a9/receipts" \
    -H "Authorization: $Authorization" \
    -H "Content-Type: application/json; charset=utf-8" \
    --data-raw "$body"
```

> Header Parameters
- **Authorization** should respect the following schema:

```json
{
  "type": "string",
  "default": "Token "
}
```


```json
{
  "type": "string",
  "enum": [
    "application/json; charset=utf-8"
  ],
  "default": "application/json; charset=utf-8"
}
```

> Body Parameters
- **body** should respect the following schema:

```json
{
  "type": "string",
  "default": "{\"method\":\"EMAIL\",\"destination\":\"daniel@mytappr.com\"}"
}
```
