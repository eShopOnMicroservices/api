# 4. Use OAS for RESTful API

Date: 2024-06-08

## Status

Accepted

Amends [2. Serve multiple APIs](0002-serve-multiple-apis.md)

## Context

[connect](https://connectrpc.com) doesn't allow overriding http paths and verbs
due to gRPC compatability requirements.

## Decision

Use [OpenAPI Spec](https://www.openapis.org) to model and generate RESTful API stubs.

## Rationale

1. **Scalability**: RESTful APIs known to be good at scaling in terms of
   cognitive load thanks to the tree-like structure of the resources.
2. **Caching support**: Adopting HTTP verbs gives as support of the inthernet
   infrastructure caching and correct idempotency guarantees.

## Implications

1. **Time Consuming**: Requires one more spec to develop and maintain.
