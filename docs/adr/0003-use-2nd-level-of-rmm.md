# 3. Use 2nd level of the RMM

Date: 2024-06-06

## Status

Accepted

## Context

There is [RMM](https://en.wikipedia.org/wiki/Richardson_Maturity_Model) which
is widely adopted when talking about implementing RESTful API.

## Decision

Use 2nd level(resources + verbs).

## Rationale

1. **Scalability**: RESTful APIs known to be good at scaling in terms of
   cognitive load thanks to the tree-like structure of the resources.
2. **Caching support**: Adopting HTTP verbs gives as support of the inthernet
   infrastructure caching and correct idempotency guarantees.
3. **Time saving**: HATEOAS is probably the most complex part of the RESTful API
   which at the same time gives less functionality, so ignoring it frees up a
   lot of time resources.

## Implications

1. **Documentation coupling**: Since we don't provide possible interactions
   with resources via HATEOAS, frontend developers are forced to use the
   documentation, probably in the format of [OpenAPI
   3.0](https://www.openapis.org) as this is the most popular REST API
   specification format.
