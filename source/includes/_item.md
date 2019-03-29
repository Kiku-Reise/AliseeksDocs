
# Product API

## Get Product

```http
POST /v1/products HTTP/1.1
{
	"productId": "32826897725",
	"currency": "USD",
	"locale": "en_US",
	"country": "US",
	"quantity": 1,
	"components": [
	  "variations",
	  "shipping",
	  "html_description"
	]
}
```

> The above command returns JSON structured like this:

```json
{
    "id": "32826897725",
    "categoryId": "200000346",
    "companyId": "214558387",
    "sellerId": "202046246",
    "detailUrl": "https://www.aliexpress.com/item/32826897725/32826897725.html",
    "title": "Office Bow Tie Blouse Women Lantern Sleeve White Button Necktie Shirts Female Elegant Work Shirt Casual Tops New 2018 Spring",
    "statusId": 0,
    "status": "active",
    "countPerLot": 1,
    "wishListCount": 8587,
    "unit": "piece",
    "multiUnit": "pieces",
    "seller": {
        "storeId": 516346,
        "storeUrl": "http://m.aliexpress.com/store/storeHome.htm?sellerAdminSeq=202046246",
        "storeName": "YUNSHAN E-commerce CO.,LTD Store",
        "sellerLevel": "31-s",
        "positiveFeedbackRate": "96.3"
    },
    "reviews": {
        "fiveStarCount": 131,
        "fourStarCount": 20,
        "threeStarCount": 1,
        "twoStarCount": 6,
        "oneStarCount": 2,
        "totalCount": 0,
        "positiveCount": 151,
        "negativeCount": 8,
        "neutralCount": 1,
        "ratings": "4.7"
    },
    "trade": {
        "sold": 739
    },
    "promotion": {
        "discount": "11",
        "timeLeft": {
            "days": 1,
            "hours": 3,
            "minutes": 50,
            "seconds": 2
        }
    },
    "productImages": [
        "https://ae01.alicdn.com/kf/HTB1zBLQHkKWBuNjy1zjq6AOypXaa.jpg_960x960.jpg_.webp",
        "https://ae01.alicdn.com/kf/HTB13mbkl5MnBKNjSZFoq6zOSFXaD.jpg_960x960.jpg_.webp",
        "https://ae01.alicdn.com/kf/HTB1GmYCyZuYBuNkSmRyq6AA3pXaE.jpg_960x960.jpg_.webp",
        "https://ae01.alicdn.com/kf/HTB1VVzqy2iSBuNkSnhJq6zDcpXaB.jpg_960x960.jpg_.webp",
        "https://ae01.alicdn.com/kf/HTB1DjsqHkyWBuNjy0Fpq6yssXXab.jpg_960x960.jpg_.webp",
        "https://ae01.alicdn.com/kf/HTB1u37GHbGYBuNjy0Foq6AiBFXay.jpg_960x960.jpg_.webp"
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
    "htmlDescription": "<p align=\"center\"><a href=\"https://www.aliexpress.com/item/LOSSKY-Knitted-Dress-Women-Elegant-Long-Sleeve-Sashes-Winter-Mini-Party-Dresses-2018-Autumn-Jumper-Casual/32903148144.html\"></a></p> <p align=\"center\"><a href=\"https://www.aliexpress.com/item/Summer-Women-Lace-Dress-Sexy-Backless-V-neck-Beach-Dresses-2018-Fashion-Sleeveless-Spaghetti-Strap-White/32875342721.html\"></a></p> <p align=\"center\"><a href=\"https://www.aliexpress.com/item/2016-New-Women-s-Winter-Fashion-Casual-Warm-Wool-Shirts-Blouse-Women-s-Long-Sleeve-Plus/32789435835.html\"></a><a href=\"http://www.aliexpress.com/item/anywhere/32789435835.html\"></a><a href=\"http://www.aliexpress.com/item/anywhere/32789435835.html\"><img src=\"http://ae01.alicdn.com/kf/HTB1AtOJXyDxK1RjSsD4q6z1DFXaZ.jpg\" width=\"950\" /></a></p> <p align=\"center\"><br /></p> <p align=\"center\">  <kse:widget data-widget-type=\"relatedProduct\" id=\"24210853\" title=\"YOUHUIQ\" type=\"custom\"></kse:widget></p> <p align=\"center\"><a href=\"https://www.aliexpress.com/item/LOSSKY-Fashion-Clothes-Vestidos-Women-Dress-2018-Autumn-Winter-Velvet-Dress-Female-O-Neck-Long-Sleeve/32919443041.html\"></a></p> <p align=\"center\"><a href=\"https://www.aliexpress.com/item/LOSSKY-Fashion-Clothes-Vestidos-Women-Dress-2018-Autumn-Winter-Dress-Female-O-Neck-Long-Sleeve-Lace/32919443041.html\"></a></p> <p align=\"center\"><a href=\"https://www.aliexpress.com/item/LOSSKY-Fashion-Clothes-Vestidos-Women-Dress-2018-Autumn-Winter-Dress-Female-O-Neck-Long-Sleeve-Lace/32919443041.html\"></a></p> <p align=\"center\"><a href=\"https://www.aliexpress.com/item/Summer-Women-Lace-Dress-Sexy-Backless-V-neck-Beach-Dresses-2018-Fashion-Sleeveless-Spaghetti-Strap-White/32875342721.html\"></a></p> <p><a href=\"https://www.aliexpress.com/item/Summer-Women-Lace-Dress-Sexy-Backless-V-neck-Beach-Dresses-2018-Fashion-Sleeveless-Spaghetti-Strap-White/32875342721.html\"></a></p> <p align=\"center\"><a href=\"https://www.aliexpress.com/item/Sexy-Summer-Button-Beach-Boho-Bohemian-Dress-Women-2018-Floral-Print-Polka-Dots-Striped-17-Colors/32866446904.html\"></a></p> <p align=\"center\">&nbsp;<img src=\"http://ae01.alicdn.com/kf/HTB1TtglinJYBeNjy1zeq6yhzVXar.jpg\" /></p> <table style=\"margin:0px auto;width:95%;font-size:20px;\" border=\"1\" cellspacing=\"0\" cellpadding=\"0\" align=\"center\">  <tbody>   <tr>    <td colspan=\"11\"><p style=\"color:#000000;\">1.The size system of different brands is different.</p><p style=\"color:#000000;\">2.Please refer to the below detail size information before order. Thanks!</p><p style=\"color:#000000;\">3.Measurement difference from 1-3cm,1 cm=0.39 inch</p></td>   </tr>   <tr style=\"background-color:#ffffff;\">    <td style=\"text-align:center;\">Size/Tag</td>    <td style=\"text-align:center;\" colspan=\"2\">S</td>    <td style=\"text-align:center;\" colspan=\"2\">M</td>    <td style=\"text-align:center;\" colspan=\"2\">L</td>    <td style=\"text-align:center;\" colspan=\"2\">XL</td>   </tr>   <tr style=\"background-color:#ffffff;\">    <td style=\"text-align:center;color:#000000;\">Cm/Inch</td>    <td style=\"text-align:center;\">Cm</td>    <td style=\"text-align:center;\">Inch</td>    <td style=\"text-align:center;\">Cm</td>    <td style=\"text-align:center;\">Inch</td>    <td style=\"text-align:center;\">Cm</td>    <td style=\"text-align:center;\">Inch</td>    <td style=\"text-align:center;\">Cm</td>    <td style=\"text-align:center;\">Inch</td>   </tr>   <tr style=\"background-color:#ffffff;\">    <td style=\"text-align:center;\">Length</td>    <td style=\"text-align:center;\">65</td>    <td style=\"text-align:center;\">25.61</td>    <td style=\"text-align:center;\">66</td>    <td style=\"text-align:center;\">26</td>    <td style=\"text-align:center;\">67</td>    <td style=\"text-align:center;\">26.4</td>    <td style=\"text-align:center;\">68</td>    <td style=\"text-align:center;\">26.79</td>   </tr>   <tr style=\"background-color:#ffffff;color:#000000;\">    <td style=\"text-align:center;color:#000000;\">Bust</td>    <td style=\"text-align:center;\">83</td>    <td style=\"text-align:center;\">32.7</td>    <td style=\"text-align:center;\">87</td>    <td style=\"text-align:center;\">34.28</td>    <td style=\"text-align:center;\">91</td>    <td style=\"text-align:center;\">25.85</td>    <td style=\"text-align:center;\">95</td>    <td style=\"text-align:center;\">37.43</td>   </tr>   <tr style=\"background-color:#ffffff;\">    <td style=\"text-align:center;\">Waist</td>    <td style=\"text-align:center;\">76</td>    <td style=\"text-align:center;\">29.94</td>    <td style=\"text-align:center;\">80</td>    <td style=\"text-align:center;\">31.52</td>    <td style=\"text-align:center;\">84</td>    <td style=\"text-align:center;\">33.1</td>    <td style=\"text-align:center;\">88</td>    <td style=\"text-align:center;\">34.67</td>   </tr>   <tr style=\"background-color:#ffffff;color:#000000;\">    <td style=\"text-align:center;color:#000000;\">Shoulder</td>    <td style=\"text-align:center;\">35</td>    <td style=\"text-align:center;\">13.79</td>    <td style=\"text-align:center;\">36</td>    <td style=\"text-align:center;\">14.18</td>    <td style=\"text-align:center;\">37</td>    <td style=\"text-align:center;\">14.58</td>    <td style=\"text-align:center;\">38</td>    <td style=\"text-align:center;\">14.97</td>   </tr>  </tbody> </table> <p align=\"center\">&nbsp;</p> <p align=\"center\"><img src=\"http://ae01.alicdn.com/kf/HTB14M6JflsmBKNjSZFFq6AT9VXa5.jpg\" width=\"920\" /></p> <p align=\"center\">&nbsp;</p> <p align=\"center\">&nbsp;</p> <p align=\"center\"><img src=\"http://ae01.alicdn.com/kf/HTB1HEfsl3LD8KJjSszeq6yGRpXaq.jpg\" width=\"850\" /></p> <p align=\"center\"><img src=\"http://ae01.alicdn.com/kf/HTB1K5SHd.o09KJjSZFDq6z9npXaO.jpg\" width=\"850\" /></p> <p align=\"center\"><img src=\"http://ae01.alicdn.com/kf/HTB1GdjhlZrI8KJjy0Fhq6zfnpXaU.jpg\" width=\"850\" /></p> <p align=\"center\"><img src=\"http://ae01.alicdn.com/kf/HTB1WjbRdAfb_uJkSmRyq6zWxVXaj.jpg\" width=\"850\" /></p> <p align=\"center\"><img src=\"http://ae01.alicdn.com/kf/HTB1LSrAl4rI8KJjy0Fpq6z5hVXaX.jpg\" width=\"850\" /></p> <p align=\"center\"><img src=\"http://ae01.alicdn.com/kf/HTB1SjS7l_nI8KJjSszgq6A8ApXa5.jpg\" width=\"850\" /></p> <p align=\"center\"><img src=\"http://ae01.alicdn.com/kf/HTB1hOzRl4PI8KJjSspoq6x6MFXah.jpg\" width=\"850\" /></p> <p align=\"center\"><img src=\"http://ae01.alicdn.com/kf/HTB1EZ_Dl3vD8KJjy0Flq6ygBFXaE.jpg\" width=\"850\" /></p> <p align=\"center\"><img src=\"http://ae01.alicdn.com/kf/HTB1qcXQdAfb_uJjSsrbq6z6bVXaV.jpg\" width=\"795\" /></p> <p align=\"center\"><img src=\"http://ae01.alicdn.com/kf/HTB1u5nGeNHI8KJjy1zbq6yxdpXau.jpg\" width=\"795\" /></p> <p align=\"center\"><img alt=\"aeProduct.getSubject()\" src=\"http://ae01.alicdn.com/kf/HTB1I1BpXDzGK1JjSspkq6xNUpXa9.jpg\" width=\"570\" /></p> <p align=\"center\"><img alt=\"aeProduct.getSubject()\" src=\"http://ae01.alicdn.com/kf/HTB1k4UwXw2DK1JjSZFOq6ybwFXaV.jpg\" width=\"574\" /></p> <p align=\"center\"><img alt=\"aeProduct.getSubject()\" src=\"http://ae01.alicdn.com/kf/HTB1RzVqXDzGK1JjSspnq6yVgXXae.jpg\" width=\"553\" /></p> <p align=\"center\"><img alt=\"aeProduct.getSubject()\" src=\"http://ae01.alicdn.com/kf/HTB1G9BrXE_FK1Jjy0Fnq6zXfXXa5.jpg\" width=\"562\" /></p> <p align=\"center\"><img alt=\"aeProduct.getSubject()\" src=\"http://ae01.alicdn.com/kf/HTB1x9NqXDzGK1JjSspaq6xPmpXaK.jpg\" width=\"589\" /></p> <p align=\"center\"><img src=\"http://ae01.alicdn.com/kf/HTB1btOjiXGWBuNjy0Fbq6z4sXXaw.jpg\" /></p> <div style=\"margin:0px auto;\">  <p style=\"overflow:hidden;height: 1.0px;padding: 0;margin: 0;\">12341</p>  <div style=\" text-align: center;\">   <div style=\"text-align: center;clear: both; padding:5px 0; display: inline-block;\">    <table border=\"0\" cellpadding=\"0\" cellspacing=\"0\">     <tbody>      <tr>       <td> <a href=\"http://www.aliexpress.com/item/anywhere/32855699106.html\"><img style=\"margin: 1px; border: 0px currentColor; \" src=\"http://ae01.alicdn.com/kf/HTB18xBAXojrK1RkHFNRq6ySvpXam.jpg\" /></a></td>       <td> <a href=\"http://www.aliexpress.com/item/anywhere/32966159357.html\"><img style=\"margin: 1px; border: 0px currentColor; \" src=\"http://ae01.alicdn.com/kf/HTB1Qgr_binrK1RjSsziq6xptpXaw.jpg\" /></a></td>       <td> <a href=\"http://www.aliexpress.com/item/anywhere/32964399629.html\"><img style=\"margin: 1px; border: 0px currentColor; \" src=\"http://ae01.alicdn.com/kf/HTB19bwfbdfvK1RjSszhq6AcGFXaA.jpg\" /></a></td>       <td> <a href=\"http://www.aliexpress.com/item/anywhere/32959780076.html\"><img style=\"margin: 1px; border: 0px currentColor; \" src=\"http://ae01.alicdn.com/kf/HTB1XYT1be6sK1RjSsrbq6xbDXXaX.jpg\" /></a></td>      </tr>      <tr>       <td> <a href=\"http://www.aliexpress.com/item/anywhere/32975058140.html\"><img style=\"margin: 1px; border: 0px currentColor; \" src=\"http://ae01.alicdn.com/kf/HTB1e.7abhrvK1RjSszeq6yObFXaz.jpg\" /></a></td>       <td> <a href=\"http://www.aliexpress.com/item/anywhere/32959018011.html\"><img style=\"margin: 1px; border: 0px currentColor; \" src=\"http://ae01.alicdn.com/kf/HTB1Vib4bifrK1RjSspbq6A4pFXaq.jpg\" /></a></td>       <td> <a href=\"http://www.aliexpress.com/item/anywhere/32730724140.html\"><img style=\"margin: 1px; border: 0px currentColor; \" src=\"http://ae01.alicdn.com/kf/HTB1ArFAXiLxK1Rjy0Ffq6zYdVXah.jpg\" /></a></td>       <td> <a href=\"http://www.aliexpress.com/item/anywhere/32955412325.html\"><img style=\"margin: 1px; border: 0px currentColor; \" src=\"http://ae01.alicdn.com/kf/HTB1ILQdbh2rK1RkSnhJq6ykdpXaI.jpg\" /></a></td>      </tr>     </tbody>    </table>   </div>  </div>  <div style=\"clear: both;\"></div> </div> <table style=\"margin:0px auto;width:95%;\" border=\"0\" cellspacing=\"0\" cellpadding=\"0\" align=\"center\">  <tbody>   <tr>    <td style=\"text-align:center;font-family:Georgia,serif;color:#0e0101;font-size:18px;\">More products click on the picture below to enter the shop</td>   </tr>   <tr>    <td style=\"text-align:center;font-family:Georgia,serif;color:#f71013;font-size:36px;\"><a href=\"https://yunshan.aliexpress.com/store/516346?spm=2114.10010108.0.0.4da6c4b6CZg8rN\"><img alt=\"\" src=\"http://ae01.alicdn.com/kf/HTB1DJc3hASWBuNjSszdq6zeSpXaX.jpg\" width=\"950\" height=\"300\" /></a> </td>   </tr>   <tr>    <td style=\"text-align:center;font-family:Georgia,serif;color:#f71013;font-size:36px;\"><img alt=\"\" src=\"http://ae01.alicdn.com/kf/HTB1LtShif9TBuNjy0Fcq6zeiFXav.jpg\" width=\"950\" height=\"80\" /> </td>   </tr>   <tr>    <td style=\"text-align:center;\"><img alt=\"\" src=\"http://ae01.alicdn.com/kf/HTB1rd8Ldi6guuRjy0Fmq6y0DXXaT.jpg\" width=\"950\" height=\"635\" /> </td>   </tr>   <tr>    <td style=\"text-align:center;\"><img alt=\"\" src=\"http://ae01.alicdn.com/kf/HTB1EmKYNVXXXXX1XpXXq6xXFXXXN.jpg\" width=\"950\" height=\"49\" /> </td>   </tr>   <tr>    <td style=\"text-align:center;\"><img alt=\"\" src=\"http://ae01.alicdn.com/kf/HTB1nqJPiKySBuNjy1zdq6xPxFXat.jpg\" width=\"950\" height=\"508\" /> </td>   </tr>   <tr>    <td style=\"text-align:center;\">     <div>      <div>       <p><strong>Wholesale and drop shipping are both welcomed?</strong> </p>       <p>For wholesale,we will offer discount or free express shipping which only takes 3-7 days to arrive.</p>       <p>For drop shipping,we could send the goods to your customers directly and won\\'t leave information about us if you\\'d like to.</p>       <p>&nbsp;</p>       <p><strong>How can</strong>&nbsp;<strong>I&nbsp;track my parcel?</strong> </p>       <p>You can track your parcel on the following website using your tracking number: www.17track.net/en &nbsp;(Copied to the browser to open)</p>       <p>&nbsp;</p>       <p><strong>What can I do when purchase protection time is running out?</strong> </p>       <p>If your purchase protection time is running out, please contact us and we can help you to extend it. So your money will not go to my account.<span>.</span> </p>      </div>     </div></td>   </tr>  </tbody> </table>",
    "priceSummary": {
        "originalAmount": {
            "min": {
                "currency": "USD",
                "value": "16.49"
            },
            "max": {
                "currency": "USD",
                "value": "16.09"
            }
        },
        "unitOriginalAmount": {
            "min": {
                "currency": "USD",
                "value": "16.49"
            },
            "max": {
                "currency": "USD",
                "value": "16.09"
            }
        },
        "discountedAmount": {
            "min": {
                "currency": "USD",
                "value": "14.32"
            },
            "max": {
                "currency": "USD",
                "value": "14.68"
            }
        },
        "unitDiscountedAmount": {
            "min": {
                "currency": "USD",
                "value": "15"
            },
            "max": {
                "currency": "USD",
                "value": "14"
            }
        },
        "bulkAmount": {
            "min": {
                "currency": "USD",
                "value": "13.30"
            },
            "max": {
                "currency": "USD",
                "value": "14.25"
            }
        },
        "unitBulkAmount": {
            "min": {
                "currency": "USD",
                "value": "13.30"
            },
            "max": {
                "currency": "USD",
                "value": "14.25"
            }
        }
    },
    "prices": [
        {
            "originalPrice": {
                "currency": "USD",
                "value": "16.49"
            },
            "discountedPrice": {
                "currency": "USD",
                "value": "14.68"
            },
            "bulkPrice": {
                "currency": "USD",
                "value": "13.97"
            },
            "bulkQuantity": 2,
            "skuImage": "https://ae01.alicdn.com/kf/HTB18_ObHxWYBuNjy1zkq6xGGpXaX.jpg_120x120q90.jpg_.webp",
            "stock": 50,
            "properties": [
                {
                    "propertyId": 14,
                    "valueId": 29,
                    "valueName": "White",
                    "valueDisplayName": "White"
                },
                {
                    "propertyId": 5,
                    "valueId": 361385,
                    "valueDisplayName": "L"
                }
            ]
        },
        {
            "originalPrice": {
                "currency": "USD",
                "value": "16.49"
            },
            "discountedPrice": {
                "currency": "USD",
                "value": "14.68"
            },
            "bulkPrice": {
                "currency": "USD",
                "value": "13.97"
            },
            "bulkQuantity": 2,
            "skuImage": "https://ae01.alicdn.com/kf/HTB18_ObHxWYBuNjy1zkq6xGGpXaX.jpg_120x120q90.jpg_.webp",
            "stock": 47,
            "properties": [
                {
                    "propertyId": 14,
                    "valueId": 29,
                    "valueName": "White",
                    "valueDisplayName": "White"
                },
                {
                    "propertyId": 5,
                    "valueId": 361386,
                    "valueDisplayName": "M"
                }
            ]
        },
        {
            "originalPrice": {
                "currency": "USD",
                "value": "16.09"
            },
            "discountedPrice": {
                "currency": "USD",
                "value": "14.32"
            },
            "bulkPrice": {
                "currency": "USD",
                "value": "13.59"
            },
            "bulkQuantity": 2,
            "skuImage": "https://ae01.alicdn.com/kf/HTB18_ObHxWYBuNjy1zkq6xGGpXaX.jpg_120x120q90.jpg_.webp",
            "stock": 49,
            "properties": [
                {
                    "propertyId": 14,
                    "valueId": 29,
                    "valueName": "White",
                    "valueDisplayName": "White"
                },
                {
                    "propertyId": 5,
                    "valueId": 100014064,
                    "valueDisplayName": "S"
                }
            ]
        },
        {
            "originalPrice": {
                "currency": "USD",
                "value": "16.49"
            },
            "discountedPrice": {
                "currency": "USD",
                "value": "14.68"
            },
            "bulkPrice": {
                "currency": "USD",
                "value": "13.97"
            },
            "bulkQuantity": 2,
            "skuImage": "https://ae01.alicdn.com/kf/HTB18_ObHxWYBuNjy1zkq6xGGpXaX.jpg_120x120q90.jpg_.webp",
            "stock": 50,
            "properties": [
                {
                    "propertyId": 14,
                    "valueId": 29,
                    "valueName": "White",
                    "valueDisplayName": "White"
                },
                {
                    "propertyId": 5,
                    "valueId": 100014065,
                    "valueDisplayName": "XL"
                }
            ]
        }
    ],
    "shipping": [
        {
            "company": "ePacket",
            "serviceName": "EMS_ZX_ZX_US",
            "tracking": true,
            "amount": {
                "currency": "USD",
                "value": "0.0"
            },
            "discount": "100",
            "commitDays": 60,
            "shipFrom": "CN",
            "deliveryTime": {
                "from": 25,
                "to": 25
            }
        },
        {
            "company": "AliExpress Standard Shipping",
            "serviceName": "CAINIAO_STANDARD",
            "tracking": true,
            "amount": {
                "currency": "USD",
                "value": "2.58"
            },
            "discount": "60",
            "commitDays": 60,
            "shipFrom": "CN",
            "deliveryTime": {
                "from": 23,
                "to": 23
            }
        }
    ]
}
```

This endpoint is the preferred endpoint for retrieving **realtime** product
information from AliExpress. This endpoint provides all the same data
as *GetProductDetails*, *GetProductShipping*, *GetProductVariations*, 
and *GetProductHTMLDescription*.

Parameter | Type | Default | Description | Allowed Values
--------- | ---- | ------- | ----------- | --------------
productId | string | empty | The product ID to retrieve. |
currency | string | USD | The currency that prices should be returned | [See supported realtime currencies.](#currency)
locale | string | en_US | The locale that the product and information should be returned in. | [See locales](#locale)
country | string | US | The country used when fetching shipping information (See supported ship to countries below)
sendGoodsCountry | string | null | The country where goods should be shipped from (See supported ship to countries below)
quantity | integer | 1 | The quantity desired to order
components | string[] | empty | List of information to retrieve, allowed values are `variations`, `shipping`, and `html_description`

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

## Get Product Reviews

```http
POST /v1/products/reviews HTTP/1.1
{
	"productId": "32844651460",
	"page": 1
}
```

> The above command returns JSON structured like this:

```json
{
    "currentPage": 1,
    "totalCount": 772,
    "totalPages": 39,
    "reviews": [
        {
            "buyerName": "S***a",
            "buyerCountry": "UA",
            "buyerRating": "100",
            "reviewDate": "2019-03-13",
            "review": "В Украину за 17 дней, трек отслеживался только по Китаю. Все работает",
            "translatedReview": "In ukraine in 17 days, the track was tracked only in china. Everything works",
            "images": [
                "https://ae01.alicdn.com/kf/UTB8rlmPJSnEXKJk43Ubq6zLppXaH.jpg"
            ],
            "shipping": "Bpost International",
            "downVotes": 0,
            "upVotes": 0
        },
        {
            "buyerName": "M***d",
            "buyerCountry": "NL",
            "buyerRating": "100",
            "reviewDate": "2019-01-09",
            "review": "Looks good. I have not tested yet, but then I will know of it is much noise. Thank you!",
            "translatedReview": "Looks good. I have not tested yet, but then I will know of it is much noise. Thank you!",
            "images": [
                "https://ae01.alicdn.com/kf/UTB8H2OXnbPJXKJkSafSq6yqUXXaK.jpg",
                "https://ae01.alicdn.com/kf/UTB8kFR5ndnJXKJkSaiyq6AhwXXaN.jpg",
                "https://ae01.alicdn.com/kf/UTB8eu5yGVfFXKJk43Otq6xIPFXaL.jpg",
                "https://ae01.alicdn.com/kf/UTB88nafnevJXKJkSajhq6A7aFXaE.jpg"
            ],
            "shipping": "China Post Ordinary Small Packet Plus",
            "downVotes": 0,
            "upVotes": 0
        }
    ]
}
```

This endpoint allows retrieving product reviews in **realtime** from AliExpress.

Parameter | Type | Default | Description | Allowed Values
--------- | ---- | ------- | ----------- | --------------
productId | string | empty | The product ID to retrieve. |
page | integer | 1 | The page number of reviews to retrieve
country | string | US | The country where the product will be shipped from (See supported ship to countries below)

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
            "stock": 50,
            "bulkQuantity": 2,
            "imageUrl":  "https://ae01.alicdn.com/kf/HTB18_ObHxWYBuNjy1zkq6xGGpXaX.jpg_120x120q90.jpg_.webp"
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
            "stock": 50,
            "bulkQuantity": 2,
            "imageUrl":  "https://ae01.alicdn.com/kf/HTB18_ObHxWYBuNjy1zkq6xGGpXaX.jpg_120x120q90.jpg_.webp"
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

## Get Product Transaction History

```http
POST /v1/products/transactions HTTP/1.1
{
  "productId": "32826897725",
  "page": 1
}
```

> The above command returns JSON structured like this:

```json
{
    "count": 1039,
    "transactions": [
        {
            "id": "98290654042210",
            "name": "P***.",
            "countryCode": "fr",
            "quantity": 1,
            "date": "2019-01-29T07:46:00Z",
            "unit": "piece"
        },
        {
            "id": "98526313392210",
            "name": "P***.",
            "countryCode": "fr",
            "quantity": 1,
            "date": "2019-01-29T07:44:00Z",
            "unit": "piece"
        }
    ]
}
```

This endpoint returns the transaction history of an item on AliExpress.

The recent transactions includes the date of the transaction and the quantity purchased, along with the country code
of the customer.

Parameter | Type | Default | Description | Allowed Values
--------- | ---- | ------- | ----------- | --------------
productId | string | null | The product ID to retrieve. |
page | integer | 1 | The page to retrieve | [1-50] 
