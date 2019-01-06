
# Product API

## Get Product Details

```http
POST /v1/products/details HTTP/1.1
{
	"productId": "32826897725",
	"currency": "AUD",
	"locale": "en_US"
}
```

> The above command returns JSON structured like this:

```json
{
    "id": "32826897725",
    "categoryId": "200000346",
    "sellerId": "202046246",
    "detailUrl": "https://www.aliexpress.com/item/32826897725/32826897725.html",
    "title": "Office Bow Tie Blouse Women Lantern Sleeve White Button Necktie Shirts Female Elegant Work Shirt Casual Tops New 2018 Spring",
    "productImages": [
        "https://ae01.alicdn.com/kf/HTB1zBLQHkKWBuNjy1zjq6AOypXaa.jpg_960x960.jpg_.webp",
        "https://ae01.alicdn.com/kf/HTB13mbkl5MnBKNjSZFoq6zOSFXaD.jpg_960x960.jpg_.webp",
        "https://ae01.alicdn.com/kf/HTB1GmYCyZuYBuNkSmRyq6AA3pXaE.jpg_960x960.jpg_.webp",
        "https://ae01.alicdn.com/kf/HTB1VVzqy2iSBuNkSnhJq6zDcpXaB.jpg_960x960.jpg_.webp",
        "https://ae01.alicdn.com/kf/HTB1DjsqHkyWBuNjy0Fpq6yssXXab.jpg_960x960.jpg_.webp",
        "https://ae01.alicdn.com/kf/HTB1u37GHbGYBuNjy0Foq6AiBFXay.jpg_960x960.jpg_.webp"
    ],
    "promotions": [
        {
            "maxAmount": {
                "currency": "AUD",
                "value": "21.5"
            },
            "minAmount": {
                "currency": "AUD",
                "value": "20.97"
            },
            "discount": "9",
            "timeLeft": {
                "days": 0,
                "hours": 3,
                "minutes": 27,
                "seconds": 0
            },
            "stock": 382
        }
    ],
    "attributes": [
        {
            "name": "Brand Name",
            "id": 2,
            "value": "LOSSKY",
            "valueId": "201785910"
        },
        {
            "name": "Material",
            "id": 10,
            "value": "Polyester,Cotton",
            "valueId": "48,47"
        },
        {
            "name": "Clothing Length",
            "id": 200000303,
            "value": "Regular",
            "valueId": "200001122"
        },
        {
            "name": "Style",
            "id": 326,
            "value": "Casual",
            "valueId": "200000072"
        }
    ],
    "prices": [
        {
            "maxAmount": {
                "currency": "AUD",
                "value": "23.62"
            },
            "maxAmountPerPiece": {
                "currency": "AUD",
                "value": "23.62"
            },
            "minAmount": {
                "currency": "AUD",
                "value": "23.04"
            },
            "minAmountPerPiece": {
                "currency": "AUD",
                "value": "23.04"
            },
            "minimumPurchase": 1,
            "processingTime": "7",
            "bulkOption": {
                "price": {
                    "currency": "AUD",
                    "value": "22.44"
                },
                "discount": "5",
                "bulkOrderCount": 2
            }
        }
    ],
    "statusId": 0,
    "countPerLot": 1,
    "wishListCount": 7355,
    "unit": "piece",
    "multiUnit": "pieces",
    "reviews": {
        "fiveStarCount": 140,
        "fourStarCount": 25,
        "threeStarCount": 4,
        "twoStarCount": 2,
        "oneStarCount": 3,
        "totalCount": 0,
        "positiveCount": 165,
        "negativeCount": 5,
        "neutralCount": 4,
        "ratings": "4.7"
    },
    "trade": {
        "sold": 1557
    },
    "skuProperties": [
        {
            "propertyId": 14,
            "propertyName": "Color",
            "values": [
                {
                    "propertyValueName": "Sky blue",
                    "propertyValueId": 173,
                    "propertyValueDisplayName": "Blue"
                },
                {
                    "propertyValueName": "White",
                    "propertyValueId": 29,
                    "propertyValueDisplayName": "White"
                }
            ]
        },
        {
            "propertyId": 5,
            "propertyName": "Size",
            "values": [
                {
                    "propertyValueName": "S",
                    "propertyValueId": 100014064,
                    "propertyValueDisplayName": "S"
                },
                {
                    "propertyValueName": "M",
                    "propertyValueId": 361386,
                    "propertyValueDisplayName": "M"
                },
                {
                    "propertyValueName": "L",
                    "propertyValueId": 361385,
                    "propertyValueDisplayName": "L"
                },
                {
                    "propertyValueName": "XL",
                    "propertyValueId": 100014065,
                    "propertyValueDisplayName": "XL"
                }
            ]
        }
    ]
}
```

This endpoint allows retrieving **realtime** product information from AliExpress.
The product information is retrieved by `Product ID` and can be modified by 
`currency` and `locale`.

Parameter | Type | Default | Description | Allowed Values
--------- | ---- | ------- | ----------- | --------------
productId | string | empty | The product ID to retrieve. |
currency | string | USD | The currency that prices should be returned | [See supported realtime currencies.](#currency)
locale | string | en_US | The locale that the product and information should be returned in. | [See locales](#locale)

## Get Product Shipping

```http
POST /v1/products/shipping HTTP/1.1
{
	"productId": "32826897725",
	"country": "US",
	"quantity": 1
}
```

> The above command returns JSON structured like this:

```json
{
    "options": [
        {
            "company": "Seller's Shipping Method",
            "serviceName": "Other",
            "tracking": false,
            "amount": {
                "currency": "USD",
                "value": "0.0"
            },
            "discount": "100",
            "commitDays": 60,
            "shipFrom": "CN",
            "deliveryTime": {
                "from": 21,
                "to": 39
            }
        },
        {
            "company": "AliExpress Standard Shipping",
            "serviceName": "CAINIAO_STANDARD",
            "tracking": true,
            "amount": {
                "currency": "USD",
                "value": "20.84"
            },
            "discount": "60",
            "commitDays": 60,
            "shipFrom": "CN",
            "deliveryTime": {
                "from": 14,
                "to": 17
            }
        },
        {
            "company": "DHL",
            "serviceName": "DHL",
            "tracking": true,
            "amount": {
                "currency": "USD",
                "value": "25.26"
            },
            "discount": "87",
            "commitDays": 30,
            "shipFrom": "CN",
            "deliveryTime": {
                "from": 7,
                "to": 14
            }
        }
    ]
}
```

This endpoint allows retrieval of **realtime** product shipping information.

Parameter | Type | Default | Description | Allowed Values
--------- | ---- | ------- | ----------- | --------------
productId | string | empty | The product ID to retrieve. |
country | string | US | The country that the product will be shipped to. (See supported ship to countries below) |
quantity | integer | 1 | The amount that will be shipped. |

### Supported Ship To Countries

AD, AE, AF, AG, AI, AL, ALA, AM,
AN, AO, AR, AS, ASC, AT, AU, AU,
AW, AZ, BA, BB, BD, BE, BE, BF, BG,
BH, BI, BJ, BLM, BM, BN, BO, BQ, BR,
BR, BS, BT, BW, BY, BZ, CA, CA, CC, CF,
CG, CH, CI, CK, CL, CL, CM, CO, CR, CV,
CW, CX, CY, CZ, DE, DE, DJ, DK, DM, DO,
DZ, EAZ, EC, EE, EG, ER, ES, ES, ET, FI, FJ, FK, FM,
FO, FR, FR, GA, GBA, GD, GE, GF, GGY, GH, GI, GL, GM, 
GN, GP, GQ, GR, GT, GU, GW, GY, HK, HN, HR, HT, HU, 
ID, IE, IL, IL, IN, IQ, IS, IT, IT, JEY, JM, JO, JP, 
KE, KG, KH, KI, KM, KN, KR, KS, KW, KY, KZ, LA, LB, 
LC, LI, LK, LR, LS, LT, LU, LV, LY, MA, MAF, MC, MD, 
MG, MH, MK, ML, MM, MN, MNE, MO, MP, MQ, MR, MS, MT, 
MU, MV, MW, MX, MY, MZ, NA, NC, NE, NF, NG, NI, NL, 
NL, NO, NP, NR, NU, NZ, OM, PA, PE, PF, PG, PH, PK, 
PL, PL, PM, PR, PS, PT, PW, PY, QA, RE, RO, RU, RU, 
RW, SA, SB, SC, SE, SG, SGS, SI, SK, SL, SM, SN, SO, SR, 
SRB, SS, ST, SV, SX, SZ, TC, TD, TG, TH, TJ, TLS, TM, 
TN, TO, TR, TT, TV, TW, TZ, UA, UG, UK, UK, US, US, 
UY, UZ, VA, VC, VE, VG, VI, VN, VU, WF, WS, YE, YT, 
ZA, ZM, ZR, ZW 

## Get Product Variations

```http
POST /v1/products/variations HTTP/1.1
{
	"productId": "32826897725",
	"currency": "AUD",
	"locale": "en_US"
}
```

> The above command returns JSON structured like this:

```json
{
    "variations": [
        {
            "propertyIdentifiers": [
                {
                    "propertyId": 14,
                    "propertyValueId": 173,
                    "propertyValueName": "Sky blue"
                },
                {
                    "propertyId": 5,
                    "propertyValueId": 361385
                }
            ],
            "propertyValueIds": [
                173,
                361385
            ],
            "productId": "32826897725",
            "price": {
                "currency": "AUD",
                "value": "23.62"
            },
            "stock": 50
        },
        {
            "propertyIdentifiers": [
                {
                    "propertyId": 14,
                    "propertyValueId": 173,
                    "propertyValueName": "Sky blue"
                },
                {
                    "propertyId": 5,
                    "propertyValueId": 361386
                }
            ],
            "propertyValueIds": [
                173,
                361386
            ],
            "productId": "32826897725",
            "price": {
                "currency": "AUD",
                "value": "23.62"
            },
            "stock": 50
        }
    ]
}
```

This endpoint returns stock and pricing for all variations of a particular product.

The property mapping information can be found by cross mapping
the [Product Detail](#get-product-details) response.

Parameter | Type | Default | Description | Allowed Values
--------- | ---- | ------- | ----------- | --------------
productId | string | empty | The product ID to retrieve. |
country | string | US | The country that the product will be shipped to. (See supported ship to countries below) |
quantity | integer | 1 | The amount that will be shipped. |

## Get Product HTML Description

```http
POST /v1/products/description/html HTTP/1.1
{
	"productId": "32826897725"
}
```

> The above command returns JSON structured like this:

```json
{
    "description": "<kse:widget data-widget-type=\"relatedProduct\" id=\"34324485\" title=\"Dress\" type=\"relation\"></kse:widget> <h1 style=\"text-align: center;\"> Hot Summer beach Dress Sexy Women Casual Sleeveless Beach Short Dress Tassel Solid White Mini Lace Dress Plus Size Drop Shipping </h1> <p align=\"left\"> <span style=\"font-family:Arial;font-size:large;\"><b><span style=\"font-style:italic;background-color:#FF6699;\">Item specifics</span></b></span></p> <ul>  <li> <p align=\"left\" style=\"margin:10px;\"> <span style=\"font-size:11pt;background-color:#FFFFFF;font-family:Arial;\">Gender:Women</span> </p> </li>  <li> <p align=\"left\" style=\"margin:10px;\">"
}
```

This endpoint returns the HTML product description as seen on the AliExpress.

The description will be returned in HTML which means that there can be embedded images and
HTML formatting.

Parameter | Type | Default | Description | Allowed Values
--------- | ---- | ------- | ----------- | --------------
productId | string | null | The product ID to retrieve. |
