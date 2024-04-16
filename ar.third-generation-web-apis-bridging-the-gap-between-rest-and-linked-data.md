---
id: 9uw9k0p43dvgxy8sg4iki00
title: Third Generation Web Apis Bridging the Gap between Rest and Linked Data
desc: ''
updated: 1713289453176
created: 1713222373047
---

- https://www.markus-lanthaler.com/research/third-generation-web-apis-bridging-the-gap-between-rest-and-linked-data.pdf
- author: @markus-lanthaler

## Highlights

### Basic Concepts and Technologies

On the Web, contracts are based on media types and protocols. Applications can thus be built by composing various well-defined build- ing blocks. Media types define the data and processing models as well as the serialization formats. Protocols describe interaction models that extend the capabilities of (the more or less generic) media types...

the contracts are centrally owned instead of being owned by the server. This allows the independent evolution of clients and servers as both are coupled to these central contracts instead of being coupled to each other.

instead of relying on upfront agreement of all aspects of interaction, parts of the contract can be communicated or negotiated at runtime.

instead of relying on implicit state control-flows as described above, all communication is stateless, meaning that each request from the client to the server must contain all the infor- mation necessary for the server to understand the request

The challenge in designing RESTful systems is to select the most appro- priate media type(s) as the core of the application-specific contract.