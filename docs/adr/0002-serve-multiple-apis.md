# 2. Serve multiple APIs

Date: 2024-06-04

## Status

Accepted

## Context

Different frontends, whetever it is web single-page app or mobile app have
various page compositions, so standard REST is not the best fit for
all of these frontends.

## Decision

Use

- [connect](https://connectrpc.com) for both RPC and REST APIs.
- [graphql](https://graphql.org) for API with query language support.

## Rationale

1. **Web compatibility**: HTTP v1.1 support out of the box without any proxy.

   The original [GRPC](https://grpc.io) is not capable to work over HTTP v1.1
   and therefore communicate with modern web JS/TS frontends without
   [grpc-web](https://github.com/grpc/grpc-web), which is effectively a proxy
   server.

2. **Frontend-oriented approach**: Frontend is free to choose API to use or
   maybe even mix them.

## Implications

1. **Stack bloating**: Using connect and graphql and 3 API architectural
   styles(RPC, REST, Query Language) at the same time is obviously a huge step
   forward [bloated
   stack](https://www.aomni.com/blog/is-your-tech-stack-too-costly-complex-or-bloated).
