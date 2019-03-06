
# Search API

## Search Products (Realtime)

```http
POST /v1/search/realtime HTTP/1.1
{
  "text": "battery backup",
  "category": "200003482",
  "priceRange": {
    "from": 12.50,
    "to": 30.00
  },
  "attributes": [
    {
      "id": "16",
      "value": "256"
    }
  ],
  "shipToCountry": "US",
  "shipFromCountry": "CN",
  "sort": "BEST_MATCH",
  "skip": 20
}

```

> The above command returns JSON structured like this:

```json
{
    "aggregation": {
        "totalCount": 1522577,
        "shipFromCountries": [
            "US",
            "CN"
        ],
        "attributes": [
          {
            "id": "16",
            "value": "Color",
            "values": [
              {
                "id": "256",
                "name": "Blue",
                "color": "Blue",
                "count": 567
              },
              {
                "id": "872",
                "name": "Red",
                "color": "Red",
                "count": 90
              }
            ]
          }
        ]
    },
    "items": [
        {
            "id": "32827273458",
            "imageUrl": "http://ae01.alicdn.com/kf/HTB1M4ztXUrrK1RkSne1q6ArVVXam.jpg",
            "title": "KPYTOMOA Boho Vintage Mini Dress Women 2018 Summer Casual",
            "ratings": 4.6,
            "orders": 670,
            "freight": {
                "price": {
                    "currency": "USD",
                    "value": "0"
                }
            },
            "priceOptions": [
                {
                    "type": "pc_price",
                    "amount": {
                        "currency": "USD",
                        "value": "12.79"
                    }
                },
                {
                    "type": "app_price",
                    "amount": {
                        "currency": "USD",
                        "value": "12.59"
                    }
                }
            ]
        }
    ]
}
```

This endpoint allows searching AliExpress in **realtime** using different criteria. The data retrieved by this
endpoint is the same that you would get from searching on AliExpress. This can be used for product sourcing,
finding dropshipping items or dynamically displaying products on a site.

### HTTP Request

`POST https://api.aliseeks.com/v1/search/realtime`

### Body Parameters

Parameter | Type | Default | Description | Allowed Values
--------- | ---- | ------- | ----------- | --------------
text | string | empty | The search text used to search for products by name |
sort | string | BEST_MATCH | Defines how the matched items should be sorted. | `BEST_MATCH`, `HIGHEST_PRICE`, `LOWEST_PRICE`, `NUMBER_OF_ORDERS`, `SELLER_RATING`, `NEWEST_TO_OLDEST`
category | integer | empty | The category of the item | [See valid categories](/aliexpress/category)
priceRange | Range | null | A price filter to apply to matched items. |
attributes | attribute[] | null | A list of selected attributes to refine the search by. |
shipToCountry | string | empty | The country where the product will be shipped to |
shipFromCountry | string | empty | The country where the product should ship from |
skip | integer | 0 | The number of matched items to skip | [0 - 5000]

## Search Products (Non-realtime)

```http
POST /v1/search HTTP/1.1
{
  "text": "phone charger",
  "sort": "BEST_MATCH",
  "currency": "USD",
  "category": 200000147,
  "orderRange": {
    "from": 50
  },
  "ratingsRange": {
    "from": 4.0,
    "to": 5.0
  },
  "quantityRange": {
    "from": 0,
    "to": 1
  },
  "priceRange": {
    "from": 2.00,
    "to": 50.00
  },
  "freightTypes": [
    "ePacket"
  ],
  "sellers": [
    "738716"
  ],
  "storeNames": [
    "Shop1828218 Store"
  ],
  "skip": 0,
  "limit": 25,
  "scrollPagination": false
}

```

> The above command returns JSON structured like this:

```json
{
  "aggregation": {
    "totalCount": 4947,
    "skip": 0,
    "limit": 25,
    "scrollIdentifier": "DnF1ZXJ5VGhlbkZldGNoBQAAAAAAAD"
  },
  "items": [
    {
        "id": "32818641835",
        "title": "1PCS Hunting Duck Commander Duck Picker Call Mallard Duck Call",
        "categoryId": 200000147,
        "imageUrl": "https://ae01.alicdn.com/kf/HTB1RxisSXXXXXbaXpXXq6xXFXXXG.jpg_960x960.jpg_.webp",
        "detailUrl": "https://www.aliexpress.com/item/32818641835/32818641835.html",
        "lotSize": 1,
        "lotUnit": "piece",
        "price": {
            "currency": "USD",
            "value": "9.990"
        },
        "ratings": 5,
        "orders": 2,
        "freight": {
            "price": {
                "currency": "USD",
                "value": "0.0"
            },
            "type": "ePacket"
        },
        "seller": {
            "storeName": "OSPRO FISHING TACKLE & HUNTING CO.,LTD",
            "positiveFeedback": 13388,
            "totalFeedback": 14227
        }
    }
  ]
}
```

This endpoint allows searching the Aliseeks Product database using different criteria. This can be used for 
product sourcing, finding dropshipping items or dynamically displaying products on a site.

For deep pagination, set `scrollPagination` to `true` and use the `scrollIdentifier` returned in the `aggregation.scrollIdentifier` field
to retrieve the next page of results. Every sub-sequent request will have an `aggregation.scrollIdentifier`, use the latest returned
value to retrieve the next page of results.

### HTTP Request

`POST https://api.aliseeks.com/v1/search`

### Body Parameters

Parameter | Type | Default | Description | Allowed Values
--------- | ---- | ------- | ----------- | --------------
text | string | empty | The search text used to search for products by name |
sort | string | BEST_MATCH | Defines how the matched items should be sorted. | `PRODUCT_ID`, `BEST_MATCH`, `MONTHLY_TRANSACTION_RATE`, `WHOLESALE_PRICE`, `ITEM_RATING`, `ORDERS`, `TRANSACTIONS`, `UPDATE_TIME`
sortDirection | string | ASC | Defines the direction that the items should be sorted. | `ASC`, `DESC`
category | integer | empty | The category of the item | [See valid categories](/aliexpress/category)
includeSubcategories | boolean | false | When this is set to `true`, we will include all the products in subcategories of `category` | `true` or `false`
currency | string | USD | The currency of the prices in the matched items. | [See supported non-realtime currencies.](#currency)
ratingsRange | Range | null | A rating filter to apply to matched items. |
quantityRange | Range | null | A lot size (sold by quantity) to apply to matched items. |
priceRange | Range | null | A non-wholesale price filter to apply to matched items. | 
unitPriceRange | Range | null | A wholesale price filter to apply to matched items. |
orderRange | Range | null | A number of orders filter to apply to matched items. |
freightTypes | string[] | null | Freight types filter to apply to matched items. You can use this filter to find items that ship with ePacket. | `ePacket` ... many more, exhaustive list coming soon.
sellers | integer[] | null | A seller filter to retrieve items that are sold by particular seller IDs. |
storeNames | string[] | null | A list of store names to retrieve items that are sold by a particular store name. |
skip | integer | 0 | The number of matched items to skip | [0 - 5000]
limit | integer | 50 | The number of matched items to return | [5 - 50]
scrollPagination | boolean | false | Use for deep pagination, set this to true and use the `scrollIdentifier` returned to retrieve the next page of results | `true` or `false`
scrollIdentifier | string | empty | Use for deep pagination, set this to the previously retrieved scroll identifier. This value can change between requests, please use the latest one. |

## Search Products By Image (Realtime)

> You can obtain an `uploadKey` by using the Upload Image API.

```http

POST /v1/search/image HTTP/1.1
{
  "uploadKey": "abcdefg.jpg",
  "currency": "USD",
  "category": 6000
}

```

> The above command returns JSON structured like this:

```json
{
  "selectedCategoryId": 3000041,
  "categories": [
    {
      "id": 40001,
      "name": "Shirts"
    },
    {
      "id": 3000041,
      "name": "Electronics"
    }
  ],
  "items": [
    {
      "id": "32279008015",
      "title": "SANYO  New Circular fan modified car electric turbocharger fan 4A 13V 6 * 6.5cm * 7.6cm diameter 9CR0612POJ50",
      "imageUrl": "http://ae01.alicdn.com/kf/HTB1r1Q3SFXXXXauaXXXq6xXFXXXZ.jpg_350x350.jpg",
      "price": {
          "currency": "USD",
          "value": "17.2"
      },
      "orders": 1
    }
  ]
}
```

This endpoint allows performing a realtime AliExpress search by image. You will need to
upload an image using the [Upload Image API](#upload-image).

<aside class="info">
To obtain an <code>uploadKey</code> you will need to use the <a href="#upload-image">Upload Image API</a> to
upload an image.
</aside>

This endpoint will automatically select the most relavent category and provide a list of items that match the Search Image.
You can invoke this API with any of the returned categories to obtain a list of items that match the Search Image and
the particular category.

### HTTP Request

`POST https://api.aliseeks.com/v1/search/image`

### Request Parameters

Parameter | Type | Default | Description | Allowed Values
--------- | ---- | ------- | ----------- | --------------
uploadKey | string | empty | The file key provided when an image is uploaded using the [Upload Image API](#upload-image) |
currency | string | USD | The currency that prices should be returned | [See supported realtime currencies.](#currency)
category | integer | null | The category to search in | [See valid categories](/aliexpress/category)

## Search Best Selling Products (Realtime)

```http
POST /v1/search/bestSelling HTTP/1.1
{
  "range": "top",
  "category": "all",
  "skip": 20,
  "locale": "en_US",
  "currency": "USD"
}

```

> The above command returns JSON structured like this:

```json
{
    "items": [
        {
            "id": "32287093437",
            "title": "LongWay Vintage Big Round Flower Gold color Silver color Statement Drop Earrings For Women Crystal Wedding Earrings SER140389",
            "imageUrl": "http://g04.a.alicdn.com/kf/HTB1ayPsLFXXXXcMXXXXq6xXFXXX1/New-Arrival-Big-Round-Drop-Earrings-For-Women-Real-Gold-Silver-Plated-Brincos-Pendientes-Crystal-Statement.jpg_350x350.jpg",
            "ratings": "4.7",
            "orders": 157,
            "detailUrl": "http://www.aliexpress.com/item/New-Arrival-Big-Round-Drop-Earrings-For-Women-Real-Gold-Silver-Plated-Brincos-Pendientes-Crystal-Statement/32287093437.html?sdom=655.123089.110643.0_32287093437",
            "storeDetailUrl": "http://www.aliexpress.com/store/product/New-Arrival-Big-Round-Drop-Earrings-For-Women-Real-Gold-Silver-Plated-Brincos-Pendientes-Crystal-Statement/728483_32287093437.html?sdom=655.123089.110643.0_32287093437",
            "priceOptions": [
                {
                    "type": "pc_price",
                    "originalAmount": {
                        "currency": "USD",
                        "value": "3.9"
                    },
                    "amount": {
                        "currency": "USD",
                        "value": "1.99"
                    }
                },
                {
                    "type": "app_price",
                    "originalAmount": {
                        "currency": "USD",
                        "value": "3.9"
                    },
                    "amount": {
                        "currency": "USD",
                        "value": "1.95"
                    }
                }
            ]
        }
    ]
}
```

This endpoint allows searching best selling `weekly` or `top` AliExpress products in multiple categories in **realtime**. This can be used to
find the best selling products provided by AliExpress and then using these products for dropshipping or reselling on other sites.

### HTTP Request

`POST https://api.aliseeks.com/v1/search/bestSelling`

### Body Parameters

Parameter | Type | Default | Description | Allowed Values
--------- | ---- | ------- | ----------- | --------------
range | string | top | Either search for `top` or `weekly` best selling items | `top` `weekly`
category | string | electronics | The category to search for best selling items. Only certain categories are allowed per range. See below. | `all` `fashion` `sports` `health_beauty` `home_garden` `kids_baby` `automotive` `men` `women`
skip | integer | 0 | The number of matched items to skip | [0 - 5000]
locale | string | en_US | The locale that the product and information should be returned in. | [See locales](#locale)
currency | string | USD | The currency that prices should be returned | [See supported realtime currencies.](#currency)

When finding `top` best selling items the categories `all`, `fashion`, `electronics`, `sports`, `health_beauty`, `kids_baby`,
`home_garden`, `automotive` are supported.

When finding `weekly` best selling items the categories `woman`, `men`, `electronics`, `sports`, `health_beauty`, `kids_baby`
`automotive` are supported.

## Upload Image

> This request is not a JSON body, rather it is Form Data. Please check your
language's client documentation for more information on how to send multipart form data 
file requests.

```http

POST /v1/search/image HTTP/1.1
Content-Type: multipart/form-data
{
  "file": "file-binary-data"
}

```

> The above command returns JSON structured like this:

```json
{
  "uploadKey": "UTB8NelmDOaMiuJk43PTq6ySmXXaD.jpg"
}
```

This endpoint allows an image to be uploaded which can then be used for
[Image Search](#search-products-by-image).

There is about a ~4MB size limit on file uploads, if you have trouble with this limit then please let us know.

## Upload Image With URL

> You can obtain an `uploadKey` by using the Upload Image API.

```http

POST /v1/search/image/upload HTTP/1.1
{
  "url": "https://assets.pernod-ricard.com/uk/media_images/test.jpg"
}

```

> The above command returns JSON structured like this:

```json
{
  "uploadKey": "UTB8NelmDOaMiuJk43PTq6ySmXXaD.jpg"
}
```

### HTTP Request

`POST https://api.aliseeks.com/v1/search/image/upload`

### Request Parameters

Parameter | Type | Default | Description | Allowed Values
--------- | ---- | ------- | ----------- | --------------
url | string | empty | The URL to download an image from | Limited to 4MB


This endpoint allows an image to be uploaded which can then be used for
[Image Search](#search-products-by-image).

There is about a ~4MB size limit on file uploads, if you have trouble with this limit then please let us know.
