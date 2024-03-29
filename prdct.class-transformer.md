---
id: x05e83huk3vudu94nado2e3
title: Class Transformer
desc: 'Decorator-based transformation, serialization, and deserialization between objects and classes.'
updated: 1701362247289
created: 1700947496599
author: "@dave"
repo: https://github.com/typestack/class-transformer
class: c.product
similar: 
  - "[[prdct.superserial]]"
  - "[[prdct.esserializer]]"
  - "[[prdct.typemanager-ts]]"
  - "[[prdct.typedjson]]"
  - "[[prdct.jackson-js]]"
category: "[[c.software.serializer]]"
tags: [serialization, deserialization]
---


## Features

- In case the nested object can be of different types, you can provide an additional options object, that specifies a discriminator. The discriminator option must define a property that holds the subtype name for the object and the possible subTypes that the nested object can converted to. A sub type has a value, that holds the constructor of the Type and the name, that can match with the property of the discriminator.