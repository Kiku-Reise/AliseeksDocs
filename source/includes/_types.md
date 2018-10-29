
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
