---
id: es9890m243wgxrgytaiofx2
title: JSON Hyper-Schema
desc: 'a JSON Schema vocabulary for annotating JSON documents with hyperlinks and instructions for processing and manipulating remote JSON resources'
updated: 1674588674818
created: 1674588427919
---


## [[c.Example]]

Here is an example hyper-schema that adds a single link, with the IANA-registered link relation type "self", that is built from an instance with one known object field named "id":

```
{
    "type": "object",
    "properties": {
        "id": {
            "type": "number",
            "readOnly": true
        }
    },
    "links": [
        {
            "rel": "self",
            "href": "thing/{id}"
        }
    ]
}
                
```

If the instance is {"id": 1234}, and its base URI according to [RFC 3986 section 5.1](https://json-schema.org/draft/2019-09/json-schema-hypermedia.html#RFC3986), is "https://example.com/api/", then "https://example.com/api/thing/1234" is the resulting link's target URI.