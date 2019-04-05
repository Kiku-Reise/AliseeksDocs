
# Types

## Range

> Simple range

```json
{
  "from": 5,
  "to": 10
}
```

> Ranges are usually integers but can be doubles

```json
{
  "from": 5.2,
  "to": 10.5
}
```

A `Range` type is used to define a **to** and **from** range.

The fields of the `Range` type are **to** and **from**.

`Range`s are usually inclusive.

## Currency

> Example of a currency

```json
{
  "currency": "GBP"
}
```

Currency is represented by a currency code `string`.

Depending on whether you are calling a **realtime** or **non-realtime** endpoint,
the allowed currency codes will be different.

### Supported Realtime Currencies

AUD, BRL, CAD, CHF, CLP, EUR, GBP, IDR, KRW, MXN, NZD, PLN, RUB,
SEK, SGD, TRY, UAH, USD

### Supported non-Realtime Currencies

AUD, BRL, CAD, CHF, CLP, CNY, EUR, GBP, IDR, INR, JPY, KRW,
MXN, NZD, PLN, RUB, SEK, SGD, TRY, UAH, USD

## Locale

> Example of a locale

```json
{
  "locale": "fr_FR"
}
```

Locale is represented by a locale `string`.

Locale's are used to represent both language code and country code. The first two
characters of a locale string is the language code and the last two characters
are the country code.
[Click here](https://www.science.co.il/language/Locale-codes.php) to see a list of locale's globally.

Only a small subset of the global locales can be used in the Aliseeks API.

### Supported Locales

ar_SA, de_DE, en_US, es_ES, fr_FR, he_IL, ko_KR, pl_PL, pt_BR, ru_RU, tr_TR

## MailingAddress

> Example of a mailing address

```json
{
  "contactName": "John Smith",
  "fullName": "John Smith",
  "taxNumber": "12345",
  "phoneNumber": {
    "number": "777-777-7777",
    "countryPrefix": "+1"
  },
  "address": {
    "line1": "12345 Jolly St",
    "line2": "APT 1234",
    "city": "Denver",
    "state": "Colorado",
    "country": "US",
    "postalCode": "80123"
  }
}
```

A mailing address defines all the components needed to mail an item to a particular location.

Parameter | Type | Default | Description | Allowed Values
--------- | ---- | ------- | ----------- | --------------
contactName | string | empty | **Required** The name of the individual at the address |
fullName | string | empty | Additional name of the individual at the address |
taxNumber | string | empty | Tax identification number associated with the address |
phoneNumber.number | string | empty | **Required** The phone number for the address |
phoneNumber.countryPrefix | string | empty | **Required** The country prefix for the address |
address.line1 | string | empty | **Required** The primary street level address, e.g. 12345 Jolly St |
address.line2 | string | empty | **Required** The secondary street level address, e.g. APT 12345 |
address.city | string | empty | **Required** The city of the address |
address.state | string | empty | **Required** The state/providence of the address |
address.country | string | empty | **Required** The country code of the address, must be ISO 2 Character. |
address.postalCode | string | empty | The postal code of the address. |

## OrderLineItem

> Example of an order line item

```json
{
  "productId": 32844651460,
  "quantity": 1,
  "shippingService": "YANWEN_JYT",
  "properties": [
    {
      "id": "200009570",
      "value": "350262"
    }
  ]
}
```

An order line item defines a specific line item in an order. The shipping service can
be retrieved from calling [Get Product Shipping](#get-product-shipping). The properties are
also referred to as sku properties are the identifiers that define an AliExpress sku and can be
retrieved from calling [Get Product](#get-product).

Parameter | Type | Default | Description | Allowed Values
--------- | ---- | ------- | ----------- | --------------
productId | number | empty | **Required** The AliExpress product ID of the item |
quantity | number | empty | **Required** The number of the item |
shippingService | number | empty | **Required** The shipping service to use to ship the item, can be retrieved from [Get Product Shipping](#get-product-shipping). |
properties | property[] | empty | **Required** List of sku identifiers that define a product variation, can be retrieved from [Get Product](#get-product). |
