# Errors

> Typical error response (in this case the request is missing productId)

```json
[
    {
        "code": "NotNull",
        "field": "productId",
        "violation": "NotNull may not be null"
    }
]
```

Anything other than a **200** response status code will indicate an error.

- 403 - Forbidden access (may not have access to an API)
- 422 - Problem with the request body
- 429 - Exceeded the allowable call count (upgrade your subscription)
- 500 - Internal server problem (contact us if this persists)

Sometimes, you may get back strange responses with a **200** response. If this is the case,
please retry your request and let us know if you see persistant problems.

Again our contact is: **alex@aliseeks.com** . This API is not very mature yet
and things may change or not work properly.
