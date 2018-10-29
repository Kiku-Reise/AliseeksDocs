
# Authentication

> To authorize your requests, append a header X-Api-Client-Id with your API key:

```http
GET / HTTP/1.1
X-Api-Client-Id: Your API Key
```

```http
POST / HTTP/1.1
X-Api-Client-Id: Your API Key
{ "anyrequest": "anyrequest" } 
```

> Make sure to replace `Your API Key` with your API key available from your dashboard on [Aliseeks](https://www.aliseeks.com).

Aliseeks API uses API keys to allow access to our API. You can register for a new API key at our [developer portal](https://www.aliseeks.com/general/api).

Aliseeks expects for the API key to be included in all API requests in a header that look like the following:

`X-Api-Client-Id: Your Api Key`

<aside class="notice">
You must replace <code>Your Api Key</code> with your personal API key.
</aside>
