
# Users

Users are the merchant users and can be broken down to several roles. Typically the primary Sole Trader, Director or owner is the main user. This role is called the Primary Owner.



## Create User
To create a user for a business.

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

```ruby
# Create a user (POST)
def send_request
  uri = URI('http://api.tappr.io/v1/user')

  # Create client
  http = Net::HTTP.new(uri.host, uri.port)
  dict = {
            "email" => "user@example.com",
            "username" => "John",
            "last_name" => "Smith",
            "password" => "Password123",
            "echo" => {
                "upstream_id" => "f083ba0f-255d-4707-9c8e-dfd14a9c56db"
            },
            "first_name" => "John"
        }

```

```python
def send_request():
    # Create a user
    # POST http://api.tappr.io/v1/user

    try:
        response = requests.post(
            url="http://api.tappr.io/v1/user",
            headers={
                "Content-Type": "application/json; charset=utf-8",
            },
            data=json.dumps({
                "email": "user@example.com",
                "username": "John",
                "last_name": "Smith",
                "password": "Password123",
                "echo": {
                    "upstream_id": "8f0303bb-39a7-43f2-86bc-ce42b7ec9821"
                },
                "first_name": "John"
            })
        )
        print('Response HTTP Status Code: {status_code}'.format(
            status_code=response.status_code))
        print('Response HTTP Response Body: {content}'.format(
            content=response.content))
    except requests.exceptions.RequestException:
        print('HTTP Request failed')

```

```swift
class MyRequestController {
    func sendRequest() {
        /* Configure session, choose between:
           * defaultSessionConfiguration
           * ephemeralSessionConfiguration
           * backgroundSessionConfigurationWithIdentifier:
         And set session-wide properties, such as: HTTPAdditionalHeaders,
         HTTPCookieAcceptPolicy, requestCachePolicy or timeoutIntervalForRequest.
         */
        let sessionConfig = URLSessionConfiguration.default

        /* Create session, and optionally set a URLSessionDelegate. */
        let session = URLSession(configuration: sessionConfig, delegate: nil, delegateQueue: nil)

        /* Create the Request:
           Create a user (POST http://api.tappr.io/v1/user)
         */

        guard var URL = URL(string: "http://api.tappr.io/v1/user") else {return}
        var request = URLRequest(url: URL)
        request.httpMethod = "POST"

        // Headers

        request.addValue("application/json; charset=utf-8", forHTTPHeaderField: "Content-Type")

        // JSON Body

        let bodyObject: [String : Any] = [
            "email": "user@example.com",
            "username": "John",
            "last_name": "Smith",
            "password": "Password123",
            "echo": [
                "upstream_id": "f3036d28-cb17-4fce-bc55-9bcd63bc1f14"
            ],
            "first_name": "John"
        ]
        request.httpBody = try! JSONSerialization.data(withJSONObject: bodyObject, options: [])

        /* Start a new Task */
        let task = session.dataTask(with: request, completionHandler: { (data: Data?, response: URLResponse?, error: Error?) -> Void in
            if (error == nil) {
                // Success
                let statusCode = (response as! HTTPURLResponse).statusCode
                print("URL Session Task Succeeded: HTTP \(statusCode)")
            }
            else {
                // Failure
                print("URL Session Task Failed: %@", error!.localizedDescription);
            }
        })
        task.resume()
        session.finishTasksAndInvalidate()
    }
}


```

> Response

```shell
{
  "first_name": "John",
  "last_name": "Smith",
  "email": "user@example.com",
  "username": "@john.smith",
  "password": "Password123",
  "echo": {
    "upstream_id": ""
  }
}
```

```ruby
#<Tappr::user id=:token> JSON: {
  "first_name": "John",
  "last_name": "Smith",
  "email": "user@example.com",
  "username": "@john.smith",
  "password": "Password123",
  "echo": {
    "upstream_id": ""
  }
}
```

### Fields

|                 |                  |                    |                                    |
|:------------------------|:------------------|:--------------------|:-----------------------------------------------|
| `first_name`            |      `query`      | string (optional)   | The user's first name. |
| `last_name`             |      `query`      | string (optional)   | The user's last name. |
| `password`              |      `query`      | string (required)   | The user's unique password. |
| `email_address`         |      `query`      | string (required)   | The user's individual email address. |
| `user_phone`            |      `query`      | string (optional)   | The user's mobile phone number.  |
| `employee_id`           |      `query`      | string (optional)   | The user's unique ID. |
| `business_id`           |      `path`        | string (required)   | The business's unique ID. |
| `role_ids`              |      `query`       | string (optional)   | The user's role. |


## Get User
> Request

```shell
curl -X GET "https://api.tappr.io/user" \
    -H "Authorization: Token eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ"
```

```ruby
require 'net/http'
require 'json'

# Retrieve a user (GET )
def send_request
  uri = URI('http://api.tappr.io/v1/user')

  # Create client
  http = Net::HTTP.new(uri.host, uri.port)
  dict = {

        }
  body = JSON.dump(dict)

  # Create Request
  req =  Net::HTTP::Get.new(uri)
  # Add headers
  req.add_field "Authorization", "Bearer ***** Hidden credentials *****"
  # Add headers
  req.add_field "Content-Type", "application/json; charset=utf-8"
  # Set body
  req.body = body

  # Fetch Request
  res = http.request(req)
  puts "Response HTTP Status Code: #{res.code}"
  puts "Response HTTP Response Body: #{res.body}"
rescue StandardError => e
  puts "HTTP Request failed (#{e.message})"
end
```

```python
# Install the Python Requests library:
# `pip install requests`

import requests
import json


def send_request():
    # Retrieve a user
    # GET http://api.tappr.io/v1/user

    try:
        response = requests.get(
            url="http://api.tappr.io/v1/user",
            headers={
                "Authorization": "Bearer ***** Hidden credentials *****",
                "Content-Type": "application/json; charset=utf-8",
            },
            data=json.dumps({

            })
        )
        print('Response HTTP Status Code: {status_code}'.format(
            status_code=response.status_code))
        print('Response HTTP Response Body: {content}'.format(
            content=response.content))
    except requests.exceptions.RequestException:
        print('HTTP Request failed')
```

```swift
class MyRequestController {
    func sendRequest() {
        /* Configure session, choose between:
           * defaultSessionConfiguration
           * ephemeralSessionConfiguration
           * backgroundSessionConfigurationWithIdentifier:
         And set session-wide properties, such as: HTTPAdditionalHeaders,
         HTTPCookieAcceptPolicy, requestCachePolicy or timeoutIntervalForRequest.
         */
        let sessionConfig = URLSessionConfiguration.default

        /* Create session, and optionally set a URLSessionDelegate. */
        let session = URLSession(configuration: sessionConfig, delegate: nil, delegateQueue: nil)

        /* Create the Request:
           Retrieve a user (GET http://api.tappr.io/v1/user)
         */

        guard var URL = URL(string: "http://api.tappr.io/v1/user") else {return}
        var request = URLRequest(url: URL)
        request.httpMethod = "GET"

        // Headers

        request.addValue("Bearer ***** Hidden credentials *****", forHTTPHeaderField: "Authorization")
        request.addValue("application/json; charset=utf-8", forHTTPHeaderField: "Content-Type")

        // JSON Body

        let bodyObject: [String : Any] = [

        ]
        request.httpBody = try! JSONSerialization.data(withJSONObject: bodyObject, options: [])

        /* Start a new Task */
        let task = session.dataTask(with: request, completionHandler: { (data: Data?, response: URLResponse?, error: Error?) -> Void in
            if (error == nil) {
                // Success
                let statusCode = (response as! HTTPURLResponse).statusCode
                print("URL Session Task Succeeded: HTTP \(statusCode)")
            }
            else {
                // Failure
                print("URL Session Task Failed: %@", error!.localizedDescription);
            }
        })
        task.resume()
        session.finishTasksAndInvalidate()
    }
}


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
Get a user at a business.

### Arguments

| Field                   |                  |                    | Description                                    |
|:------------------------|:------------------|:--------------------|:-----------------------------------------------|
| `employee_id`           |      `path`      | string (required)   | The user's unique ID. |
| `business_id`           |      `path`        | string (required)   | The business's unique ID. |

## Update a user

Update a user of a business with general information or a role.

