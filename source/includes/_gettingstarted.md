# Getting Started

## Postman

The quickest way to start making requests to Aliseeks is by using our 
[Postman Collection](https://documenter.getpostman.com/view/3150332/RznFqeQE).

[Postman](https://www.getpostman.com/) allows you to manually construct requests and
send them to the API and see responses.

## Client Libraries

We vend out several client libraries to make application integration very easy. We currently
vend client libraries in the following languages:

* [C#](https://gitlab.com/aliseeksapi/aliseeks-csharp-sdk)
* [Java](https://gitlab.com/aliseeksapi/aliseeks-java-sdk)
* [Javascript](https://gitlab.com/aliseeksapi/aliseeks-javascript-sdk)
* [PHP](https://gitlab.com/aliseeksapi/aliseeks-php-sdk)
* [Python](https://gitlab.com/aliseeksapi/aliseeks-python-sdk)
* [Ruby](https://gitlab.com/aliseeksapi/aliseeks-ruby-sdk)

### Don't see your language listed?

These clients are automatically generated from
an [OpenAPI](https://github.com/OAI/OpenAPI-Specification) specification. Aliseeks
[public OpenAPI specification](https://gitlab.com/aliseeksapi/aliseeksswagger/raw/master/openapi/aliseeks.yaml) is listed available and can be used to auto-generate
custom clients that are currently not specifically vended.

There are several open source tools available for auto-generating clients. Aliseeks uses
[openapi-generator](https://github.com/OpenAPITools/openapi-generator). `openapi-generator`
can auto-generate clients in 40+ languages.  

> Generating a new client with `openapi-generator`

```bash
openapi-generator generate -i https://gitlab.com/aliseeksapi/aliseeksswagger/raw/master/openapi/aliseeks.yaml \
  -g kotlin
```

### Help needed!

Don't see your language listed? Or would like to contribute to an existing client?
You can contribute back to the community by keeping clients up to date and improving their
code quality.

All clients are generated from [AliseeksSwagger](https://gitlab.com/aliseeksapi/aliseeksswagger).
Contributions are welcomed and changes are propagated to the respective client repositories.

[Submit an issue](https://gitlab.com/aliseeksapi/aliseeksswagger/issues) if you've got an idea or suggestion.
