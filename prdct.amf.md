---
id: 7w1up1wbehh4m19sfyth3bv
title: AMF
desc: 'AML Modeling Framework is an open-source library capable of parsing and validating AML metadata documents'
updated: 1708466080488
created: 1701291818173
repo: https://github.com/aml-org/amf
supports:
  - scala
  - javascript
  - java
---

## Features

AMF natively supports the following formats:

-   YAML
-   JSON

the following semantic models:

-   WebApi (or "Web APIs" as in "APIs accessible over the network")
-   AsyncApi

and the following syntactic models:

-   JSON-LD "AMF model"
-   RAML 0.8 / 1.0 (mapped to "WebApi")
-   OpenAPI (OAS) 2.0 / 3.0 (mapped to "WebApi")
-   AsyncAPI 2.0 (mapped to "AsyncApi")

Code samples are in scala, java, and typescript   


## Description

### nordic apis

The AML Modeling Framework (AMF) is an open-source library that serves as a powerful tool for working with AsyncAPI and other API specifications. AMF is capable of parsing, transforming, validating, and rendering arbitrary models, making it an invaluable asset for developers working with AsyncAPI.

One of the key components of AMF is the API Contract Model, which contains all the information expressed in the source API document. This model can be used for validations, transformations, and conversions, making it highly versatile and adaptable to different use cases.
What sets AMF apart is its support for custom models and parsers, which can be defined using the AML (API Modeling Language) language. This allows developers to create their own models and parsers tailored to their specific needs and requirements.

To illustrate the power of AMF, let’s consider an example where an OpenAPI Specification (OAS) 3.0 API document needs to be parsed, validated, transformed, and rendered in RAML 1.0. With AMF, this can be achieved seamlessly, simplifying the process and saving valuable development time.

If you want to learn more about the AML Modeling Framework and its capabilities, various resources are available, including the official documentation, tutorials, and code examples. These resources can provide a deeper understanding of AMF and help you unlock its full potential for working with AsyncAPI and other API specifications.

## References

- https://nordicapis.com/6-asyncapi-validation-tools/