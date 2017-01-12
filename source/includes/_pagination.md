# Pagination

Endpoints such as Orders might paginate the results they return. This means that instead of returning all results in a single response, these endpoints might return some of the results, along with a 'cursor' in the response body that links to the next set of results. The current maximum is currently set at 20.



| Field       | Description                                                                   |
|:------------|:------------------------------------------------------------------------------|
| `limit`   _OPTIONAL_  | Limits the number of results per-page. Maximum 20. |
| `since`  	_OPTIONAL_  |                     |
| `before`    _OPTIONAL_  |                                                      |
