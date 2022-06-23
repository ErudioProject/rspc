**This project is a work in progress. I just wanted to try and replicate the syntax of [trpc](https://trpc.io/) in Rust**

# trpc-rs

A blazing fast and easy to use TRPC server for Rust.

## Example

You define a `trpc` router and attach resolvers to it like below. This will be very familiar if you have used [trpc](https://trpc.io/) or [GraphQL](https://graphql.org) before.

```rust
let router = trpc_rs::Router::<()>::new()
    .query("version", |_| "0.0.1")
    .mutation("helloWorld", |_| async { "Hello World!" });
```

## Features:

 - Per Request Context - Great for database connection & authentication data

## Planned Features:

 - Export working Typescript bindings using `ts_rs`
 - Replace `RequestKind` with different exec functions for each type.
 - Axum example
 - Provide arguments to resolvers
 - [Merging servers](https://trpc.io/docs/merging-routers)
 - [Middleware](https://trpc.io/docs/middlewares) & [Route Meta](https://trpc.io/docs/metadata)
 - [Error Handling](https://trpc.io/docs/error-handling)
 - [Subscriptions](https://trpc.io/docs/subscriptions)
 - Validate arguments against schema (check length is correct, check formatting (Eg. is email?), etc)
 - Maybe share input validation with frontend Typescript code?? - So your form input validation can match server validation without having to define it twice
