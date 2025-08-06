# gleam-nodejs

This development container includes:
- Gleam v1.12.0
- Erlang/OTP
- Node.js

Based on the official Gleam Docker image with Erlang support, installs Node.js
separately.

## Why Install Node.js Instead of `node-slim` Image?

The `node-slim` image does not ship with Erlang inside. Somehow, when compiling
with `gleam build`, the build does not work due to the lack of Erlang when
checking `erl -version`.

## Why Node.js?

I wanted to try to run Gleam applications in Node.js, also, while learning more
about the language and ecosystem.
