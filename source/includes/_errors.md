# Errors

> Typical error response (in this case the request is missing productId)

```http
POST /v1/search HTTP/1.1
x-error-code: NotNull
x-error-detailed-message: NotNull may not be null
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

Errors can be read from the JSON body response of the API or can be read off of the headers:
**x-error-code**, **x-error-detailed-message** .

**WARNING: This API is not very mature yet and things may change or not work properly. This API may cease to operate at
any point in time without warning. You assume all risks associated with using this API.**
