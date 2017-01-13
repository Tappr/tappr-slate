
# Fees

Merchants must collect appropriate fees or "Taxes" based on their business and the products they sell. A fee, once defined, can be associated to a category, item or all tenders.


## Get Fee List
Get all fee rates for this merchant.

>Request 

```shell 
curl -X POST "https://api.tappr.io/v1/businesses/:business_id/fees"

```

```ruby
require 'net/http'
require 'json'

# List all fees (GET )
def send_request
  uri = URI('http://api.tapp.io/v1/businesses/:business_id/fees?page=2')

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
    # List all fees
    # GET http://api.tappr.io/v1/businesses/:business_id/fees

    try:
        response = requests.get(
            url="http://api.tappr.io/v1/businesses/:business_id/fees",
            params={
                "page": "2",
            },
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
           List all fees (GET http://api.tappr.io/v1/businesses/:business_id/fees)
         */

        guard var URL = URL(string: "http://api.tappr.io/v1/businesses/:business_id/fees") else {return}
        let URLParams = [
            "page": "2",
        ]
        URL = URL.appendingQueryParameters(URLParams)
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


protocol URLQueryParameterStringConvertible {
    var queryParameters: String {get}
}

extension Dictionary : URLQueryParameterStringConvertible {
    /**
     This computed property returns a query parameters string from the given NSDictionary. For
     example, if the input is @{@"day":@"Tuesday", @"month":@"January"}, the output
     string will be @"day=Tuesday&month=January".
     @return The computed parameters string.
    */
    var queryParameters: String {
        var parts: [String] = []
        for (key, value) in self {
            let part = String(format: "%@=%@",
                String(describing: key).addingPercentEncoding(withAllowedCharacters: .urlQueryAllowed)!,
                String(describing: value).addingPercentEncoding(withAllowedCharacters: .urlQueryAllowed)!)
            parts.append(part as String)
        }
        return parts.joined(separator: "&")
    }
    
}

extension URL {
    /**
     Creates a new URL by adding the given query parameters.
     @param parametersDictionary The query parameter dictionary to add.
     @return A new URL.
    */
    func appendingQueryParameters(_ parametersDictionary : Dictionary<String, String>) -> URL {
        let URLString : String = String(format: "%@?%@", self.absoluteString, parametersDictionary.queryParameters)
        return URL(string: URLString)!
    }
}


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
> Request

```shell 
curl -X POST "https://api.tappr.io/v1/businesses/:business_id/fees"

```

```ruby
require 'net/http'
require 'json'

# Create a fee (POST )
def send_request
  uri = URI('http://api.tappr.io/v1/businesses/:business_id/fees')

  # Create client
  http = Net::HTTP.new(uri.host, uri.port)
  dict = {
            "status" => "ACTIVE",
            "calculation_phase" => "TOTAL",
            "fee_type" => "GOVERNMENT",
            "inclusion_type" => "ADDITIVE",
            "amount" => {
                "currency_code" => "AUD",
                "minor_units" => 10
            },
            "name" => "GST",
            "apply_to_custom_amount" => true
        }
  body = JSON.dump(dict)

  # Create Request
  req =  Net::HTTP::Post.new(uri)
  # Add headers
  req.add_field "Authorization", "Token "
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
    # Create a fee
    # POST http://api.tappr.io/v1/businesses/:business_id/fees

    try:
        response = requests.post(
            url="http://api.tappr.io/v1/businesses/:business_id/fees",
            headers={
                "Authorization": "Token ",
                "Content-Type": "application/json; charset=utf-8",
            },
            data=json.dumps({
                "status": "ACTIVE",
                "calculation_phase": "TOTAL",
                "fee_type": "GOVERNMENT",
                "inclusion_type": "ADDITIVE",
                "amount": {
                    "currency_code": "AUD",
                    "minor_units": 10
                },
                "name": "GST",
                "apply_to_custom_amount": True
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
           Create a fee (POST http://api.tappr.io/v1/businesses/:business_id/fees)
         */

        guard var URL = URL(string: "http://api.tappr.io/v1/businesses/:business_id/fees") else {return}
        var request = URLRequest(url: URL)
        request.httpMethod = "POST"

        // Headers

        request.addValue("Token ", forHTTPHeaderField: "Authorization")
        request.addValue("application/json; charset=utf-8", forHTTPHeaderField: "Content-Type")

        // JSON Body

        let bodyObject: [String : Any] = [
            "status": "ACTIVE",
            "calculation_phase": "TOTAL",
            "fee_type": "GOVERNMENT",
            "inclusion_type": "ADDITIVE",
            "amount": [
                "currency_code": "AUD",
                "minor_units": 10
            ],
            "name": "GST",
            "apply_to_custom_amount": true
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
		"name":  "GST",
		"status":  "ACTIVE",
		"apply_to_custom_amount":  true,
		"fee_type":  "GOVERNMENT",
		"inclusion_type":  "ADDITIVE",
		"calculation_phase":"TOTAL",
		"amount":{
			"minor_units":10,
			"currency_code":"AUD"
				}
	}

```

```ruby
	{
		"name":  "GST",
		"status":  "ACTIVE",
		"apply_to_custom_amount":  true,
		"fee_type":  "GOVERNMENT",
		"inclusion_type":  "ADDITIVE",
		"calculation_phase":"TOTAL",
		"amount":{
			"minor_units":10,
			"currency_code":"AUD"
				}
	}

```

```python
	{
		"name":  "GST",
		"status":  "ACTIVE",
		"apply_to_custom_amount":  true,
		"fee_type":  "GOVERNMENT",
		"inclusion_type":  "ADDITIVE",
		"calculation_phase":"TOTAL",
		"amount":{
			"minor_units":10,
			"currency_code":"AUD"
				}
	}

```
```swift
	{
		"name":  "GST",
		"status":  "ACTIVE",
		"apply_to_custom_amount":  true,
		"fee_type":  "GOVERNMENT",
		"inclusion_type":  "ADDITIVE",
		"calculation_phase":"TOTAL",
		"amount":{
			"minor_units":10,
			"currency_code":"AUD"
				}
	}

```

###ARGUMENTS

| Field              | Note       | Description                                                 |
|:-------------------|:-----------|:------------------------------------------------------------|
| `tax_id`        | `query` | string (Required)              |
| `business_id`        | `path` | string (Required)                 |

## Delete Fee

Delete a tax.



> Request


```shell
curl -X GET "https://api.tappr.io/businesses/:business_id/fees" \
    -H "Authorization: Token eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiYWRtaW4iOnRydWV9.TJVA95OrM7E2cBab30RMHrHDcEfxjoYZgeFONFh7HgQ"
```

> Response

```json
[ ]
```

###ARGUMENTS

| Field              | Note       | Description                                                 |
|:-------------------|:-----------|:------------------------------------------------------------|
| `tax_id`        | `query` | string (Required)              |
| `business_id`        | `path` | string (Required)                 |
