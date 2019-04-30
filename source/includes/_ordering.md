
# Ordering API

<aside class="notice">
Please contact us to enable your account for Ordering. Send us an email at alex@aliseeks.com .
Currently, we are limiting accounts with access to Ordering to paid subscribers.
</aside>

The Ordering API allows create and retrieving orders. You can place orders on behalf
of merchants that are registered to your Aliseeks account. Each merchant registered will be assigned
a unique **Merchant ID**. You can register a merchant through Aliseeks.com or by 
using the [Register Merchant endpoint](#register-merchant).

## How to Onboard a Merchant

### Single Merchant per Account
1. Join the [AliExpress Dropshipping Program.](https://home.aliexpress.com/dropshipper/ds_center.htm)
![dropshipping](dropshipping-console.jpg)

2. Onboard a merchant through the Aliseeks Console.
![slack](merchant-registration-console.jpg)

3. The **Merchant ID** is provided on the Aliseeks Console.
![slack](merchant-registration-id-console.jpg)

### Multiple Merchants per Account
1. Make sure all your merchants have agreed to the join the [AliExpress Dropshipping Program](https://home.aliexpress.com/dropshipper/ds_center.htm).
![dropshipping](dropshipping-console.jpg)
2. Onboard a merchant by redirecting to the URL provided in [Register Merchant](#register-merchant).
3. Persist the **Merchant ID** returned by the [Register Merchant](#register-merchant) API.

## Create Order

> This is only a sample request, do not use this in production. Fill in the request body with a known address, phone
number and correct product information.

```http
POST /v1/orders HTTP/1.1
{
	"merchantId": "YOUR_MERCANT_ID",
    "locale": "en_US",
    "mailingAddress": {
        "contactName": "John Modena",
        "phoneNumber": {
            "number": "7137398000",
            "countryPrefix": "+1"
        },
        "address": {
            "line1": "1600 Lamar St",
            "line2": "",
            "city": "Houston",
            "state": "Texas",
            "country": "US",
            "postalCode": "77010"
        }
    },
    "items": [
        {
            "productId": 32690828906,
            "quantity": 1,
            "shippingService": "YANWEN_JYT",
            "properties": [
                {
                    "sku": "14:29#clear"
                },
                {
                	"sku": "200000061:1454#6x8mm  70pcs"
                }
            ]
        }
    ]
}
```

> The above command returns JSON structured like this:

```json
{
    "merchantId": "YOUR_MERCHANT_ID",
    "orderIds": [
        101274465122817
    ]
}
```

<aside class="notice">
You must have a Merchant ID prior to calling this API.
</aside>

Creates an order on AliExpress. The order will be created under the account
associated with the **Merchant ID**. The order will not be paid, the AliExpress account owner will
need to click on "Pay Now" to complete the transaction, they can pay with any payment method they
would prefer.

[Use case - Create an Order Guide.](https://aliseeks.gitbook.io/docs/use-cases/create-dropshipping-order)

Parameter | Type | Default | Description | Allowed Values
--------- | ---- | ------- | ----------- | --------------
merchantId | string | empty | The Merchant ID to use when fetching the order. |
locale | [Locale](#locale) | en_US | The locale that the item is being purchased from. [Supported Locales](#locale) |
mailingAddress | [MailingAddress](#mailingaddress) | null | Mailing address information for the order. |
items | [OrderLineItem](#orderlineitem)[] | null | List of line items for the order. |

## Get Order

```http
GET /v1/orders?merchantId=AjbjasWsnzse&orderId=828752957 HTTP/1.1
```

> The above command returns JSON structured like this:

```json
{
    "id": "828752957xxx",
    "created": "2017-03-29T00:07:56Z",
    "total": {
        "currency": "USD",
        "value": "71.78"
    },
    "status": "order_completed",
    "shippingStatus": "shipped",
    "store": {
        "id": "718232",
        "name": "BIG TREE TECH Store",
        "url": "https://www.aliexpress.com/store/718232"
    },
    "shipping": [
        {
            "trackingNumber": "DH002886407AE",
            "shippingService": "CAINIAO_STANDARD"
        },
        {
            "trackingNumber": "LP00068298585456",
            "shippingService": "CAINIAO_STANDARD"
        }
    ],
    "items": [
        {
            "productId": 32602496788,
            "quantity": 2,
            "name": "50PCS 3D Printer Prusa Mendel 12v40w 6*20 Cartridge Heater Reprap 12V 40W WITH Free Shipping",
            "price": {
                "currency": "USD",
                "value": "38.89"
            }
        }
    ]
}
```

<aside class="notice">
You must have a Merchant ID prior to calling this API.
</aside>

Fetches the information for a particular Order. 

Parameter | Type | Default | Description | Allowed Values
--------- | ---- | ------- | ----------- | --------------
merchantId | string | empty | The Merchant ID to use when fetching the order. |
orderId | string | empty | The Order ID to retrieve information about. |

## Get Tracking Information

**Being implemented - Coming soon!**

Are you interested? Send us an email and let us know you want this.

## Register Merchant

```http
POST /v1/merchants HTTP/1.1
{
  "redirectUrl": "https://your-domain.com/accounts/merchants",
  "merchantId": "ExistingMerchantId"
}
```

> Please make sure to save the `merchantId` returned by this API as you will need it
to interact with an account. The above command returns JSON structured like this:

```json
{
  "merchantId": "AjbjasWsnzse",
  "redirectUrl": "https://redirect-your-customer-here.com"
}
```

<aside class="warning">
Only certain accounts are whitelisted to register merchants through the API. Please contact us
if this is something you need.
</aside>

<aside class="notice">
Your customers must reauthorize through this flow once a month or requests for this merchant will fail.
</aside>


This endpoint allows registration of merchant accounts through the API. Merchants can usually only
be registered through the Aliseeks Console, however your account may be whitelisted to use this endpoint
to allow registering more than one merchant on your account.

To register a customer account and allow placing automated orders, call this endpoint and provide a
`redirectUrl` which we will use to redirect your customer after receiving Authorization to allow Aliseeks
to place orders on their behalf.

Redirect your customer to the `redirectUrl` provided in the response. Do not reuse this `redirectUrl` between
customers. It can only be used once.

Be sure to save the `merchantId` in the response so you can use it to place or get orders on behalf of
this customer. You can optionally pass in a `merchantId` if you are re-authorizing your customer.

Parameter | Type | Default | Description | Allowed Values
--------- | ---- | ------- | ----------- | --------------
redirectUrl | string | empty | The URL that the customer will be redirected to after authorizing Aliseeks to access their AliExpress account. |
merchantId | string | empty | Optional - Can be used when re-authorizing a customer to keep a consistent Merchant ID between re-authorizations |
